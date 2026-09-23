# Prompt: Generador de videos educativos verticales (finanzas)

Crea desde cero un proyecto en Remotion + TypeScript para generar videos educativos
verticales (formato 9:16, 1080x1920, 30fps) sobre finanzas personales/inversión,
con voz en off generada por TTS. El proyecto debe ser genérico: cada video nuevo se
crea escribiendo un archivo de datos (guion), sin tocar el código de las escenas.

## Layout (3 zonas fijas en toda la pantalla)

1. **Superior (~15% de la altura):** título corto del video/tema, siempre visible,
   tipografía grande y bold, con margen seguro para no chocar con la UI de apps
   móviles (TikTok/Reels/Shorts).
2. **Centro (~55-60% de la altura):** zona de animación. Aquí se renderiza el
   componente visual de la escena actual (ver lista abajo).
3. **Inferior (~20-25% de la altura):** subtítulos básicos de la narración, sincronizados
   con el audio, revelados frase por frase (no una palabra a la vez), con buen
   contraste y máximo 2 líneas visibles a la vez.

Diseño limpio, fondo oscuro con degradado sutil, una paleta de 2-3 colores
(acento neutro + un color para "positivo/crecimiento" y otro para "negativo/riesgo"),
tipografía sans-serif bold vía Google Fonts. Deja la paleta exacta como placeholder
fácil de cambiar (archivo de constantes), ya que la identidad visual final se
definirá aparte.

## Arquitectura orientada a datos (data-driven)

- Cada video es un archivo TypeScript en `src/videos/<id>.ts` que exporta un objeto
  con: id, título, y una lista ordenada de "escenas". **Un guion puede tener tantas
  escenas como haga falta** para explicar el tema (no hay un número fijo ni máximo).
- Cada escena tiene: `type` (uno de los tipos abajo), el componente visual
  correspondiente, y una lista ordenada de "beats" (ver regla siguiente) en vez de
  un único bloque de narración.
- Un componente `VideoAssembler` genérico recorre las escenas, calcula la duración de
  cada una a partir de la duración real del audio (nunca a partir de una estimación),
  y las encadena con una transición de fundido corta (~0.3-0.4s) usando
  `@remotion/transitions`.
- Registrar todos los videos definidos en un array central para que Remotion los
  liste como composiciones independientes (una por video).

## Guion y sincronización con la narración

- **Frases cortas, no párrafos:** dentro de cada escena, la narración se escribe como
  una lista de frases cortas (una idea por frase; evita oraciones largas o
  compuestas). Cada frase corta es un "beat" independiente dentro de la escena, con
  su propio texto de voz y su propio texto de subtítulo.
- **Animación alineada a lo narrado:** cada beat debe declarar qué le pasa a la
  animación en ese instante (qué elemento aparece, cambia de valor, se resalta o
  se retira), de forma que el componente visual reaccione en sincronía con la frase
  que se está narrando en ese momento — no solo al inicio/fin de la escena completa.
  Por ejemplo, en una escena `example` con `CounterStat`, la frase "empiezas con 100
  dólares al mes" dispara la aparición del contador, y la frase siguiente "en 10 años
  se convierten en X" dispara la animación del contador subiendo hasta ese valor.
- Para repartir el tiempo de cada beat dentro del audio de la escena sin
  timestamps por palabra, generar el audio de la escena completa y estimar el
  punto de inicio de cada beat proporcionalmente a la cantidad de caracteres de las
  frases anteriores (mismo criterio ya usado para subtítulos).

## Tipos de escena

1. **`hook`**: escena de apertura con el título/pregunta gancho del video
   (ej. "¿Por qué el interés compuesto es tu mejor aliado?").
2. **`concept`**: explica un concepto con narración + subtítulos + un componente
   visual de apoyo.
3. **`comparison`**: contrasta dos opciones/escenarios lado a lado (ej. ahorrar vs.
   invertir, deuda buena vs. deuda mala).
4. **`example`**: aplica el concepto a un caso numérico concreto (ej. "$100 al mes
   durante 10 años").
5. **`cta`**: cierre con resumen/llamado a la acción (seguir, comentar, etc.).

## Componentes visuales (genéricos, reutilizables entre videos)

- **`GrowthChart`**: curva animada que crece con el tiempo (interés compuesto,
  inflación, valor de un activo).
- **`ComparisonCards`**: dos tarjetas flotantes lado a lado con ícono, cifra y
  etiqueta, para contrastar dos escenarios.
- **`MoneyFlowDiagram`**: flechas animadas mostrando el movimiento de dinero entre
  2-4 nodos (ej. sueldo → gastos → ahorro → inversión).
- **`PieBreakdown`**: gráfico circular animado que se arma por partes (ej.
  distribución de un presupuesto 50/30/20).
- **`CounterStat`**: número grande que cuenta hacia arriba/abajo hasta un valor final,
  con una etiqueta corta debajo.
- **`IconChecklist`**: lista de puntos con íconos (✓ / ✗) que aparecen en cascada.

Cada componente recibe sus datos (valores, etiquetas, colores positivo/negativo)
desde la escena del guion — no debe haber contenido de finanzas hardcodeado dentro
del componente.

## Voz en off (TTS)

- Genera la narración con la API de Voice Box en `http://127.0.0.1:17493`.
- Antes de integrarla, verifica el flujo real contra la API corriendo (no asumas
  rutas ni parámetros): listar voces disponibles, generar audio, consultar el estado
  de la generación hasta que esté completo, y descargar el archivo de audio final.
- Usa una única voz consistente en todo el proyecto (pregúntame el nombre exacto si
  no te lo indico).
- Guarda cada audio junto a su duración exacta en segundos (medida del resultado de
  la API, no estimada), y usa esa duración para calcular en frames cuánto dura cada
  escena — nunca cortes la narración ni retires el texto antes de que termine de
  hablar.
- Genera subtítulos dividiendo el texto de cada escena en frases cortas y repartiendo
  su aparición proporcionalmente a la duración del audio de esa escena (division por
  cantidad de caracteres es suficiente si no hay timestamps por palabra).

## Control de calidad obligatorio (antes de dar por terminado un video)

- **Escalado de la zona de animación**: el componente visual debe ocupar al menos
  75-80% de la altura de su zona y ~85% del ancho utilizable (márgenes seguros de
  ~80-100px a los lados en el lienzo de 1080px). Nunca dejar elementos pegados al
  borde ni sub-dimensionados.
- **Verificación con capturas**: antes de renderizar el video completo, generar
  stills (`npx remotion still <Composición> --frame=<n>`) de al menos dos escenas
  clave (la de apertura y una con animación central) y revisarlas visualmente:
  texto legible, bien alineado, sin recortes.
- **Animaciones continuas entre escenas relacionadas**: si dos escenas consecutivas
  comparten el mismo elemento visual (ej. la misma gráfica que sigue creciendo), no
  debe desmontarse ni reiniciar su animación de entrada al cambiar de escena —
  animar en base a un frame relativo al grupo completo, no al frame local de cada
  escena.
- **Hooks de React**: nunca llamar `useCurrentFrame()`, `useVideoConfig()` o
  `spring()` de forma condicional, dentro de loops o de funciones auxiliares de
  renderizado — extraer a subcomponentes propios.
- **Representación literal**: cada animación debe representar literalmente lo que
  se narra (si se habla de "interés compuesto", mostrar dinero o una curva
  creciendo — no figuras abstractas genéricas sin relación con el concepto).
- **Cero desorden visual**: sin textos largos, párrafos, ni etiquetas redundantes
  dentro de los componentes — solo números grandes, badges cortos (1-3 palabras) e
  íconos. El texto explicativo vive en el subtítulo, no en el componente visual.
- **Movimiento vivo, nunca estático**: toda escena debe tener micro-animaciones
  sutiles y continuas (oscilaciones suaves, pulsos, ensamblado progresivo de
  elementos) — nunca una tarjeta o diagrama completamente estático.
- **Revelación progresiva**: ningún elemento visual debe aparecer antes de que la
  narración lo mencione — todo se ensambla en sincronía con el beat del guion que
  se está narrando en ese instante (ver regla de "beats" arriba).
- **Cero sacudidas**: prohibido cualquier shake, vibración o salto brusco de
  elementos — solo transiciones suaves (springs, fades, easing).
- **Subtítulos autosuficientes**: cada frase en pantalla debe entenderse sola, sin
  necesidad del audio (el video debe funcionar perfectamente en silencio/mute).
- **Hilo narrativo continuo**: usar conectores explícitos entre escenas ("para
  evitar esto...", "aquí es donde entra...", "imagina que...", "por eso...") para
  que el guion se sienta como una historia progresiva y no datos sueltos.
- **Tipografía mobile-first**: tamaños grandes y bold dentro de tarjetas/badges
  (mínimo ~15-18px para etiquetas, 24-32px para cifras hero), `whiteSpace: "nowrap"`
  y padding generoso para que nada se deforme o corte.

## Protocolo de verificación final

Antes de dar por terminado cualquier video, incluir un resumen breve que confirme:
qué stills se revisaron, que el escalado cumple la regla del 85%/75-80%, que no hay
hooks condicionales, y que cada animación quedó sincronizada con el beat de
narración correspondiente.

## Primer video de ejemplo

Antes de generar nada, plantéame en una tabla las escenas propuestas (texto exacto
de narración, texto en pantalla, componente visual y duración estimada) para un
primer video de 30-45 segundos sobre **interés compuesto**, y espera mi confirmación
antes de generar audios, programar la animación o renderizar.
