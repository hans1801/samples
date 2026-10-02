Animación: "Cómo funciona un agente de IA" (motion graphics estilo After Effects)
Objetivo
Crea una animación de ~55 segundos, con calidad de motion graphics profesional
(estilo video de lanzamiento de Apple, Stripe o Linear), que explique POR SÍ SOLA,
sin narración, cómo trabaja un agente de IA como tú:
tarea → piensa → actúa con herramientas → observa el resultado → corrige errores → repite.
NO quiero un diagrama estático ni un anillo girando. Quiero tarjetas, pipelines,
tipografía cinética y cámara en movimiento, como si lo hubiera animado un motion designer.
Storyboard (puedes mejorarlo, pero respeta la progresión)

1. La tarea (0–5 s): se escribe el prompt real de esta sesión en una tarjeta; la cámara se aleja.
2. Piensa (5–12 s): la tarjeta vuela hacia un núcleo luminoso (el modelo) y se despliega
una tarjeta con el plan real en pasos.
3. Actúa (12–25 s): las tarjetas de herramientas (Read, Write, Edit, Bash…) se abren en abanico en 3D.
Cada paso real voltea su tarjeta y muestra su contenido: código escribiéndose, líneas de terminal.
Pipelines con partículas conectan cada acción con su resultado.
4. Observa (25–33 s): los resultados vuelven como paquetes de datos y se apilan en una
"ventana de contexto", con un contador de tokens subiendo.
5. Error (33–40 s): una tarjeta tiembla en rojo con un efecto de falla y muestra el error real;
aparece la corrección en verde y se resuelve.
6. Repite (40–50 s): el ciclo se acelera; las tarjetas pasan rápido por el pipeline
mientras corren contadores de pasos, archivos, tokens y tiempo.
7. Remate (50–55 s): todas las tarjetas se juntan en un marco de video que muestra
ESTA MISMA animación, una dentro de otra (efecto Droste).
Texto final: "Así funciona la IA… que acaba de crear esta animación."

Principios de motion design (obligatorios)

* Cámara en 2.5D: capas a distintas profundidades, paralaje y movimientos de cámara suaves.
* Curvas de animación profesionales: entradas y salidas suaves, pequeño rebote al llegar,
elementos que entran escalonados. Nada lineal.
* Transiciones que conectan escenas: una tarjeta se convierte en la siguiente escena,
revelados con máscaras, cortes que coinciden en forma o posición.
* Siempre algo en movimiento, pero con un solo foco claro por momento.
* Profundidad visual: brillos, sombras suaves, partículas sutiles, transparencias.

Texto en pantalla (la animación se explica sola)

* Un título corto por escena (máximo 5 palabras), con tipografía cinética:
"1. Recibe una tarea", "2. Piensa", "3. Actúa", "4. Observa", "Si falla… lo corrige", "Y repite".
* Un indicador discreto y fijo del ciclo (piensa / actúa / observa) que se ilumina según la fase.
* Cada título visible al menos 2 segundos.

Rigor (MUY IMPORTANTE)
Todo el contenido de las tarjetas debe ser REAL: al final del proceso, lee el registro de
ESTA MISMA SESIÓN (el .jsonl más reciente en ~/.claude/projects/ de esta carpeta)
y usa el prompt real, el plan real, las herramientas reales en orden, fragmentos cortos
de código o de terminal, los errores reales y sus correcciones.
Si hay demasiados pasos, agrúpalos sin cambiar el orden real.
Anonimiza: nada de rutas personales, correos ni claves.
Sonido (100% generado con código)

* Sintetiza todo el audio con código (ondas, ruido, envolventes). Sin archivos externos.
* Efectos sincronizados con cada evento: swooshes al moverse las tarjetas, clics al voltearse,
tecleo al escribirse el código, efecto de falla en el error, un tono ascendente al corregirlo
y un golpe grave en el remate.
* Una base musical electrónica sutil, también sintetizada.
* Los mismos datos que mueven la animación disparan los sonidos.
* Entrega el MP4 con el audio mezclado y, aparte, las pistas de efectos y música en WAV.

Dirección de arte

* Fondo oscuro con gradiente sutil; tarjetas con efecto de vidrio (glassmorphism).
* Un color por fase: piensa (violeta), actúa (azul), observa (verde), error (rojo).
* Tipografía sans-serif moderna; monoespaciada para código y nombres de herramientas.
[OPCIONAL: adjunto una imagen de referencia de estilo — adáptate a ella]

Formato

* 1920×1080, 30 fps (60 si el render lo permite), ~55 s, MP4.
* Solo código: sin imágenes, audios ni modelos de generación externos.

Cómo quiero que trabajes

1. Antes de programar, elige la técnica para la imagen y para el sonido, y justifícalas.
Muéstrame el plan de escenas con tiempos y el texto en pantalla de cada una.
2. Construye la animación leyendo el contenido desde un `data.json` (primero con datos de ejemplo).
3. Renderiza frames clave como PNG, revísalos visualmente y corrige lo que se vea
plano, vacío, genérico o difícil de leer. Si una escena parece un diagrama estático, rehazla.
4. Al final, lee el registro de esta sesión, genera el `data.json` real
y renderiza el video definitivo con audio.
5. Escribe un `DECISIONES.md` corto: técnicas elegidas (imagen y sonido), flujo técnico,
iteraciones, qué corregiste y tiempo total aproximado.

Límite: el render no debe tardar horas; si algo es muy pesado, simplifícalo sin perder calidad visual.
