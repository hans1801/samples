@sample.mp4 # Caso: hologramas de producto para un comercial de marca
Te paso: un comercial de 22 s generado con IA, sin texto ni interfaz.
Son 4 tomas en una tienda de electrónica premium:

1. 0–4 s: una persona entra a la tienda (sin holograma).
2. 4–10 s: una mano levanta unos audífonos y se detiene unos segundos.
3. 10–16 s: un reloj inteligente en la muñeca, que se detiene unos segundos.
4. 16–22 s: unas manos giran una cámara de fotos y se detienen unos segundos.

Después de la toma 4 agrega una tarjeta de cierre de ~3 s (el video final dura ~25 s).
Quiero que agregues, solo con código, hologramas de producto que parezcan parte de la escena,
como en un comercial de una marca tecnológica premium.
Qué debes hacer

1. Analiza el video: confirma los cortes entre tomas (tiempos de arriba), detecta la pausa de cada producto
y su posición en cada frame. Sigue al producto durante el acercamiento de la cámara.
2. Crea una marca ficticia (nombre, colores, tipografía, estilo de la interfaz)
y aplícala igual en las 3 tomas y en la tarjeta de cierre.
Antes de decidir, propón 2–3 direcciones de marca, elige una y explica por qué.
3. Diseña el holograma de cada producto: un contorno luminoso alrededor del producto
y un panel flotante en el espacio libre del encuadre, sin tapar el producto ni las manos.
Aparece desde el primer instante que se muestra el producto y aprovecha todo el espacio del holograma para mostrar la información del producto.
4. Decide cómo presentar la información. Cada panel tiene 7–8 líneas (ver `datos.json`).
No se lee todo de golpe en 3 segundos: decide la jerarquía, el orden y el ritmo con que aparecen.
5. Sonido: sintetiza con código los sonidos de la interfaz (aparición, cada línea, cierre),
disparados por los mismos eventos que la animación, y mézclalos con el audio original del video.

Datos (ponlos en `datos.json`; el render debe leerlo todo de ahí)

* Audífonos: Audífonos Pulse PX-7 · Cancelación activa de ruido: −32 dB · Batería: 40 h · Carga rápida: 10 min = 5 h · Bluetooth 5.3 · Códec LDAC · Peso: 254 g · ★ 4.8 (2,134 reseñas) · Antes $249 → Ahora $199 · Envío gratis mañana
* Reloj: Reloj Orbit S2 · 45 mm · Ritmo cardíaco: 72 lpm · Oxígeno en sangre: 98 % · Pasos hoy: 8,542 / 10,000 · Resistente al agua: 5 ATM · Batería: 7 días · $249 · 12 cuotas de $20.75
* Cámara: Cámara Lumen Z30 · Sensor full frame · 33 MP · Video 4K a 120 fps · Lente 35 mm ƒ/1.8 · ISO 100 – 51,200 · Estabilización en 5 ejes · Peso: 658 g (con batería) · $1,150 · Incluye lente

Si en tu marca los nombres de producto (Pulse, Orbit, Lumen) no encajan, puedes cambiarlos; explica por qué.
Formato

* Misma resolución y fps que el video original, MP4 con el audio mezclado.
* Solo código y mi video: sin modelos de generación de imagen, video ni voz.
* Además, renderiza una segunda versión cambiando solo el precio de los audífonos a $179
(editando `datos.json`) y anota cuánto tardó ese cambio.

Cómo quiero que trabajes

* Referencia de estilo: interfaces holográficas de comerciales tech premium y de películas de ciencia ficción
(vidrio translúcido, líneas finas, brillo suave, tipografía limpia). Nada "minimalista" que se vea vacío.
* Elige la técnica (seguimiento, render, composición) y justifícala antes de programar.
* Renderiza frames clave de cada toma, revísalos (legibilidad, que no tape el producto, que siga bien al objeto) y corrige.
* Si algo va a tardar más de ~45 min, avísame antes y propón una versión más simple.
* Escribe un `DECISIONES.md` con:
   * técnica y flujo técnico,
   * las direcciones de marca que propusiste, cuál elegiste y por qué,
   * qué descartaste y por qué (diseño, posición, ritmo),
   * iteraciones y correcciones,
   * tiempo total y tiempo del cambio de precio.
