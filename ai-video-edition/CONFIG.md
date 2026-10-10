Eres mi asistente de edición de video. Vas a crear desde cero, en **esta carpeta vacía**, un proyecto para editar videos con código: yo te paso mis grabaciones, audios y assets, y tú creas las animaciones, los cortes y los subtítulos con código, y los previsualizo en Remotion Studio.

**Trabaja de forma autónoma de principio a fin.** No me hagas preguntas: si algo es ambiguo, elige la opción más simple y anótala en `MAPA.md` en "Decisiones que tomé". Si algo falla al instalar, busca otra forma (Homebrew, npm, binario oficial) y sigue. Todo debe quedar **local**, en esta carpeta, sin servicios en la nube ni API keys. No toques nada fuera de esta carpeta, salvo instalar herramientas del sistema que falten (Node.js, FFmpeg).

### 1. Herramientas
Revisa e instala lo que falte, y anota la versión de cada una en `MAPA.md`:
- **Node.js** (LTS) y npm.
- **FFmpeg** y ffprobe: cortes, unir clips, extraer audio y frames, quemar subtítulos.
- **Remotion** (proyecto en blanco con TypeScript): las animaciones son componentes de React que se renderizan a video. Remotion Studio sirve para previsualizar.
- **Whisper local** (whisper.cpp vía `@remotion/install-whisper-cpp`, modelo `medium` o el que funcione en esta computadora): transcripción palabra por palabra con su segundo exacto. Es lo que permite que las animaciones entren justo cuando digo cada palabra.

### 2. Estructura de carpetas
```
.
├── CLAUDE.md              # reglas para la IA (cómo construir)
├── ESTILO.md              # dirección visual (qué se ve y por qué) ← lo más importante
├── MAPA.md                # mapa de lo que hiciste (para mí)
├── input/                 # mis grabaciones crudas (video y audio)
├── assets/                # imágenes, logos, capturas, clips de pantalla
├── public/                # lo que Remotion puede leer (copias de input/assets)
├── scripts/               # automatizaciones con FFmpeg y Whisper
├── src/
│   ├── brand/             # tokens: colores, tipografías, tamaños, movimiento
│   ├── lib/               # primitivas: texto, entradas/salidas, cámara, resaltado
│   ├── components/        # fondo y piezas reutilizables
│   └── videos/<nombre>/   # un proyecto por video (escenas + composición)
└── out/                   # renders
```

### 3. `ESTILO.md` — la dirección visual
Escríbelo completo, en español, con este contenido (adáptalo en redacción, no en las reglas):

**Identidad:** fondo oscuro dark-tech (grid sutil y brillos), neón en los acentos, no en todo. Tutoriales de IA y automatización. Render 4K 3840×2160 a 30 fps; todas las medidas en px 4K.

**Paleta (un acento protagonista por escena, máximo dos):**
| Token | Hex | Significado |
|---|---|---|
| cyan | #00FBFF | marca / información |
| green | #39FF14 | éxito, automático, "sí" |
| gold | #FFD700 | cierre, CTA |
| orange | #FF9500 | manual, esfuerzo |
| purple | #BD00FF | IA, magia |
| red | #FF2D55 | error, "no", tachado |
| white / text / muted | #FFFFFF / #E2E8F0 / #94A3B8 | textos |
| surface / surfaceHi | #0B1016 / #121A24 | paneles |

**Tipografía:** Montserrat 700–900 (títulos e impacto), Inter 500–800 (texto), JetBrains Mono (código y cifras). 6 tamaños: display 220 · title 150 · header 100 · body 72 · label 56 · tag 48. **Nada por debajo de 48 px.**

**Espacio y forma:** margen seguro 200 px a los lados y 150 px arriba y abajo. Radios 20 / 40 / 72. Los paneles ocupan el 55–75 % del ancho: grande o nada.

**Movimiento:** springs `panel` (damping 28, stiffness 140) para paneles grandes, `soft` (18/120) para entradas, `pop` (14/130) para checks y sellos. Salida de 8 frames. Siempre algo vivo (flotar, pulso, push lento de cámara), pero sutil. "Despegue rápido, aterrizaje lento."

**Principios (de Vox, Hormozi, Ali Abdaal, MrBeast, Fireship y Kurzgesagt, adaptados):**
1. Todo se mueve con la voz: cada elemento entra cuando se nombra (tiempos desde la transcripción, nunca estimados).
2. Nunca más de ~3 s sin cambio visual; en el hook, cada 1–1,5 s.
3. Un énfasis por frase: la palabra clave lleva el color de acento, un resaltado o un punch de cámara.
4. Mostrar, no escribir: los conceptos se vuelven objetos, procesos, antes/después y resultados.
5. Causa → efecto visible: algo actúa (cursor, bot) y algo cambia.
6. Material real antes que ilustraciones: capturas, videos y logos del tema.
7. Texto en pantalla: 1 a 4 palabras clave. El audio ya lo dice; no repitas la narración.
8. Moderación: sin emojis voladores, sin fuente Impact con trazo neón, sin efectos de sonido en cada frase.

**8 modos visuales (uno por beat; no repetir el mismo más de 2 beats seguidos):** HOOK (1–4 palabras gigantes + el resultado final) · DEMO (mockup con cursor que hace 1–3 acciones) · PIPELINE (bot → etapas → resultado, para "automático") · VERSUS (antes/después; el perdedor en rojo, el ganador crece en verde) · DATA (contador hasta la cifra) · CODE (pocas líneas reales grandes + resaltado) · STAMP (sello o marcador sobre lo que ya está en pantalla) · PRESENTER (mi video 40 % + animación 60 %, o PiP).

**Checklist por beat:** ¿qué frase lo justifica? ¿qué modo? ¿palabra clave y su frame? ¿acción → resultado? ¿asset real? ¿hay más de 3 s sin cambio? ¿hay texto que el audio ya dice?

**Lo que NO hacemos:** captions de toda la narración en el centro, stick figures cuando hay material real, UI con texto diminuto (se reemplaza por formas e íconos), pantallas con solo un título.

### 4. `CLAUDE.md` — reglas de construcción
Resume en español: el flujo (paso 6), los comandos, que todo texto use la primitiva de texto con los tokens (nunca px, hex ni fuentes sueltas), que los tiempos salgan siempre de la transcripción con `at("palabra")`, un archivo por escena con las coordenadas como constantes en px 4K, y que antes de entregar se corra el lint (paso 5) con 0 errores. Que siempre lea `ESTILO.md` antes de diseñar.

### 5. Código base y scripts
- **`src/brand`**: tokens de la paleta, tipografías (con `@remotion/google-fonts`), tamaños, espacios, radios, springs y una función `glow(hex, fuerza)`.
- **`src/lib`**: `<T size color>` para todo texto, `useEnter` / `useExit`, `<Stage>` con margen seguro, `Camera` (push lento + punch en una palabra), `Highlight` (marcador estilo Vox), `KineticWords` (palabras que entran una a una con una en acento).
- **`src/components/DarkTechBackground.tsx`**: el fondo de todas las composiciones de animación.
- **Scripts de npm** (en `scripts/`, con Node):
  - `npm run ingest -- <audio|video> [guion.md] --video <nombre> --name part-N` → copia el archivo a `public/`, extrae el audio con FFmpeg, transcribe con Whisper palabra por palabra, alinea con el guion si lo hay, y genera `words.ts` con `at("palabra")`, `end()` y `DURATION`, más un reporte `part-N.ingest.md` (correcciones y diferencias con el guion).
  - `npm run silences -- <video> [--min 0.5] [--pad 0.12]` → detecta silencios con `silencedetect` de FFmpeg y muletillas desde la transcripción ("eh", "este", "o sea", "¿no?"…), y genera **una propuesta** `cuts.json` + un video recortado de previsualización. No pisa el original: yo decido si la acepto.
  - `npm run subs -- <video> --name part-N` → genera `.srt` desde la transcripción y una versión con subtítulos quemados con FFmpeg.
  - `npm run check -- <carpeta>` → lint de escenas: tamaños de fuente menores a 48, hex o px de fuente escritos a mano, texto de más de 4 palabras en pantalla.
  - `npm run dev` → Remotion Studio.

### 6. Flujo de trabajo (documéntalo en `CLAUDE.md`)
1. **Ingesta:** `npm run ingest` (siempre primero con un audio nuevo).
2. **Limpieza (opcional):** `npm run silences` propone cortes; yo los acepto, los ajusto o corto a mano en un editor.
3. **Beat sheet:** antes del código, una tabla en `animation-guide.md`: beat · frames · cita del audio · modo · palabra clave · acción → resultado · acento · assets · SFX sugeridos.
4. **Código:** una escena por beat o grupo de beats, tiempos desde `words.ts`.
5. **Verificación:** `npm run check` con 0 errores y `npx tsc --noEmit` limpio.
6. **Revisión visual:** 1 still por beat a 1/4 de escala, juntarlos en un mosaico con FFmpeg, revisar escala y espacios vacíos, corregir.
7. **Entrega:** render 4K sin audio para el editor, y un preview con audio.

### 7. Prueba de punta a punta (obligatoria)
1. Genera un audio de prueba de ~15 s con la voz del sistema (`say` en macOS, `espeak` en Linux) diciendo algo como: *"Esta animación se creó solo con código. Primero transcribo el audio, después detecto los silencios, y al final cada palabra aparece justo cuando la digo."*
2. Corre `ingest`, `silences` y `subs` con ese audio.
3. Crea `src/videos/demo/` con 3 beats en modos distintos (HOOK → PIPELINE → STAMP) siguiendo `ESTILO.md` y sincronizados con `words.ts`.
4. Corre `check` y `tsc`, renderiza 3 stills y un preview en baja resolución en `out/demo/`, míralos y corrige lo que se vea pequeño o vacío.

### 8. `MAPA.md` — el mapa para mí (lo último que haces)
En español simple, para alguien que no programa:
- **Mapa conceptual en Mermaid** (`flowchart`): input → ingest (FFmpeg + Whisper) → words.ts → silences (cuts.json) → beat sheet → escenas (brand + lib + ESTILO.md) → Remotion Studio → check → render → editor final.
- **Qué es cada carpeta y cada archivo importante**, en una línea.
- **Qué herramienta hace qué** (Node, Remotion, FFmpeg, Whisper) y su versión.
- **Cómo uso el proyecto con un video nuevo**, en 5 pasos con los comandos.
- **Decisiones que tomé** y **qué falló y cómo lo resolví**.
- **Ideas para personalizar el estilo** (ver abajo).

Al terminar, deja Remotion Studio listo para abrir con `npm run dev` y escribe un resumen de 5 líneas.

### 9. Hazlo tuyo (incluir en `MAPA.md` y al final de `ESTILO.md`)
Este estilo es un punto de partida, no una plantilla para copiar. Formas de variarlo:
- Pedir "cambia `ESTILO.md` a un estilo minimalista / editorial / retro" y regenerar los tokens.
- Pasar capturas o videos de referencia de otros canales y pedir que actualice `ESTILO.md` con lo que ve (paleta, ritmo, tipografía, transiciones).
- Cambiar la paleta y las fuentes en `src/brand`: todas las escenas se actualizan solas.
- Agregar modos visuales propios o quitar los que no uses.