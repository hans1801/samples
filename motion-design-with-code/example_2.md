Animación: "El taller del agente"
Objetivo
Crea una animación de 50–60 segundos que explique, POR SÍ SOLA y sin narración,
cómo trabaja un agente de IA (como tú). Usa una METÁFORA VISUAL, no un diagrama:
un pequeño robot trabajando en un taller isométrico lleno de detalles,
como un diorama vivo con cosas pasando en cada rincón.
Alguien que la vea sin sonido y sin contexto debe entender:

1. El agente recibe una tarea.
2. Trabaja en un ciclo: pensar → actuar (usar una herramienta) → observar el resultado.
3. Si algo falla, lee el error y lo corrige.
4. Todo lo que aprende se acumula en su memoria de trabajo (el contexto).
5. Repite el ciclo hasta terminar.

La metáfora (respétala, pero enriquécela)

* El robot = el agente.
* Cada herramienta = una estación del taller, con su letrero:
   * Read → biblioteca, letrero "LEER".
   * Write → imprenta, letrero "ESCRIBIR".
   * Edit → mesa de trabajo con lupa y martillo, letrero "EDITAR".
   * Bash → sala de máquinas con palancas, engranajes y vapor, letrero "EJECUTAR".
   * Otras herramientas → inventa una estación coherente con su letrero.
* Un error = una máquina se atasca y suelta chispas; el robot la repara.
* El contexto = una mochila que se va llenando visiblemente con cada paso.
* Final: la cámara se aleja; en una pantalla del taller se ve una miniatura
de ESTA animación; el robot se sienta a descansar.

Texto en pantalla (la animación debe explicarse sola)

* Letreros dentro de la escena en cada estación (en español), con el nombre real
de la herramienta en pequeño y en fuente monoespaciada.
* Un título corto por escena (máximo 6 palabras), que aparece y desaparece con suavidad.
Ej.: "1. Llega una tarea", "2. Piensa qué necesita", "3. Actúa", "4. Observa el resultado",
"Si falla… lo corrige", "El contexto crece", "Repite hasta terminar".
* Un indicador fijo y discreto del ciclo (pensar / actuar / observar)
que se ilumina según la fase actual.
* Texto final: "Así funciona la IA… que acaba de crear esta animación."
* Todo el texto debe poder leerse con calma: mantén cada título al menos 2 segundos.

Sonido (100% generado con código)

* Sintetiza todo el audio con código (ondas, ruido, envolventes). Sin archivos de audio externos.
* Efectos sincronizados con los eventos de la animación: pasos del robot, páginas,
la imprenta, engranajes, vapor, chispas del error, la reparación y una campanita al terminar.
* Una música de fondo suave en bucle, también sintetizada, que baje de volumen
cuando suenen los efectos.
* Los mismos datos que mueven la animación deben disparar los sonidos.
* Entrega el MP4 con el audio mezclado y, aparte, las pistas de efectos y de música en WAV.

Rigor (MUY IMPORTANTE)
El recorrido del robot debe ser REAL: al final del proceso, lee el registro de
ESTA MISMA SESIÓN (el .jsonl más reciente en ~/.claude/projects/ de esta carpeta)
y usa tus pasos reales, en orden, como guion del recorrido:
qué herramienta usaste, si hubo errores y cómo los corregiste.
Si hay demasiados pasos, agrúpalos sin cambiar el orden real.
Anonimiza: nada de rutas personales, correos ni claves.
Nivel de ambición

* Mucho detalle: objetos secundarios animados (engranajes, luces que parpadean,
papeles que caen, un gato durmiendo…) y algún guiño escondido al mundo de la IA.
* Cámara con movimiento: acercamientos a cada estación y un plano general al final.
* Robot expresivo: duda, se sorprende, celebra.
* Estilo: ilustración isométrica vectorial tipo diorama, colores cálidos
con acentos neón en las máquinas.
[OPCIONAL: adjunto una imagen de referencia de estilo — adáptate a ella]

Formato

* 1920×1080, 30 fps, 50–60 s, MP4.
* Solo código: sin imágenes, audios ni modelos de generación externos.

Cómo quiero que trabajes

1. Antes de programar, elige la técnica para la imagen y para el sonido, y justifícalas.
Muéstrame el plan de escenas con tiempos y el texto en pantalla de cada una.
2. Construye la escena leyendo el recorrido desde un `data.json` (primero con datos de ejemplo).
3. Renderiza frames clave como PNG, revísalos visualmente y corrige lo que se vea pobre,
vacío, genérico o difícil de leer.
4. Al final, lee el registro de esta sesión, genera el `data.json` real
y renderiza el video definitivo con audio.
5. Escribe un `DECISIONES.md` corto: técnicas elegidas (imagen y sonido), flujo técnico,
iteraciones, qué corregiste y tiempo total aproximado.

Límite: el render no debe tardar horas; si algo es muy pesado, simplifícalo sin perder detalle visual.
