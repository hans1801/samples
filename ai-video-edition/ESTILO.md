# ESTILO.md — Dirección visual

> Léelo **antes de diseñar cualquier escena**. Aquí está *qué* se ve y *por qué*. El *cómo* está en `CLAUDE.md`.

## 1. Identidad

- **Dark-tech**: fondo oscuro con grid sutil y brillos suaves que respiran (`DarkTechBackground`).
- **Neón solo en los acentos**, nunca en todo. Si todo brilla, nada destaca.
- Tema: tutoriales de **IA y automatización**.
- Render **4K 3840×2160 a 30 fps**. Todas las medidas de este documento están en **px 4K**.

## 2. Paleta

**Un acento protagonista por escena, máximo dos.**

| Token | Hex | Significado |
|---|---|---|
| `cyan` | `#00FBFF` | marca / información |
| `green` | `#39FF14` | éxito, automático, "sí" |
| `gold` | `#FFD700` | cierre, CTA |
| `orange` | `#FF9500` | manual, esfuerzo |
| `purple` | `#BD00FF` | IA, magia |
| `red` | `#FF2D55` | error, "no", tachado |
| `white` / `text` / `muted` | `#FFFFFF` / `#E2E8F0` / `#94A3B8` | textos |
| `surface` / `surfaceHi` | `#0B1016` / `#121A24` | paneles |

El color **significa algo**: si algo es manual, va en naranja; si lo hace la IA, en morado; si funcionó, en verde.

## 3. Tipografía

- **Montserrat 700–900** → títulos e impacto.
- **Inter 500–800** → texto.
- **JetBrains Mono** → código y cifras.

Seis tamaños, nada más:

| Token | px |
|---|---|
| `display` | 220 |
| `title` | 150 |
| `header` | 100 |
| `body` | 72 |
| `label` | 56 |
| `tag` | 48 |

**Nada por debajo de 48 px.** Si no cabe, sobra texto.

## 4. Espacio y forma

- Margen seguro: **200 px a los lados**, **150 px arriba y abajo**.
- Radios: **20 / 40 / 72**.
- Los paneles ocupan el **55–75 % del ancho**: grande o nada. Nada de tarjetitas perdidas en el centro.

## 5. Movimiento

| Spring | damping / stiffness | Uso |
|---|---|---|
| `panel` | 28 / 140 | paneles grandes |
| `soft` | 18 / 120 | entradas |
| `pop` | 14 / 130 | checks y sellos |

- Salida en **8 frames**.
- **Siempre algo vivo** (flotar, pulso, push lento de cámara), pero sutil.
- **"Despegue rápido, aterrizaje lento."**

## 6. Principios

Inspirados en Vox, Hormozi, Ali Abdaal, MrBeast, Fireship y Kurzgesagt, adaptados:

1. **Todo se mueve con la voz.** Cada elemento entra cuando se nombra. Los tiempos salen de la transcripción, nunca se estiman.
2. **Nunca más de ~3 s sin cambio visual.** En el hook, un cambio cada 1–1,5 s.
3. **Un énfasis por frase.** La palabra clave lleva el color de acento, un resaltado o un punch de cámara.
4. **Mostrar, no escribir.** Los conceptos se vuelven objetos, procesos, antes/después y resultados.
5. **Causa → efecto visible.** Algo actúa (cursor, bot) y algo cambia.
6. **Material real antes que ilustraciones.** Capturas, videos y logos del tema.
7. **Texto en pantalla: 1 a 4 palabras clave.** El audio ya lo dice; no repitas la narración.
8. **Moderación.** Sin emojis voladores, sin Impact con trazo neón, sin efectos de sonido en cada frase.

## 7. Los 8 modos visuales

Un modo por beat. **No repetir el mismo modo más de 2 beats seguidos.**

| Modo | Qué es | Cuándo |
|---|---|---|
| **HOOK** | 1–4 palabras gigantes + el resultado final | primeros segundos |
| **DEMO** | mockup con cursor que hace 1–3 acciones | "mira cómo se hace" |
| **PIPELINE** | bot → etapas → resultado | "automático", procesos |
| **VERSUS** | antes/después; el perdedor en rojo, el ganador crece en verde | comparaciones |
| **DATA** | contador hasta la cifra | números, ahorro de tiempo |
| **CODE** | pocas líneas reales, grandes, con resaltado | prompts, scripts |
| **STAMP** | sello o marcador sobre lo que ya está en pantalla | conclusiones, "listo" |
| **PRESENTER** | mi video 40 % + animación 60 %, o PiP | cuando hablo a cámara |

## 8. Checklist por beat

- [ ] ¿Qué frase del audio lo justifica?
- [ ] ¿Qué modo?
- [ ] ¿Cuál es la palabra clave y en qué frame (`at("…")`)?
- [ ] ¿Qué actúa y qué cambia (acción → resultado)?
- [ ] ¿Hay un asset real que pueda usar?
- [ ] ¿Hay algún tramo de más de 3 s sin cambio?
- [ ] ¿Hay texto en pantalla que el audio ya dice?

## 9. Lo que NO hacemos

- Captions de toda la narración en el centro de la pantalla.
- Stick figures cuando hay material real.
- UI con texto diminuto → se reemplaza por formas e íconos.
- Pantallas con solo un título.

## 10. Hazlo tuyo

Este estilo es un **punto de partida**, no una plantilla para copiar. Formas de variarlo:

- Pedir *"cambia `ESTILO.md` a un estilo minimalista / editorial / retro"* y regenerar los tokens de `src/brand`.
- Pasar capturas o videos de referencia de otros canales y pedir que se actualice `ESTILO.md` con lo que se ve (paleta, ritmo, tipografía, transiciones).
- Cambiar la paleta y las fuentes en `src/brand`: **todas las escenas se actualizan solas**.
- Agregar modos visuales propios o quitar los que no uses.
