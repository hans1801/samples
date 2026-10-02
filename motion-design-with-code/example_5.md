Caso: animación 3D solo con código — "El chip por dentro"
Quiero una animación 3D de 15–20 s, hecha solo con código, al nivel de la presentación de un chip
en el lanzamiento de una marca tecnológica premium.
La idea
La cámara empieza lejos de un procesador futurista flotando en la oscuridad,
se acerca, atraviesa su superficie y entra en él.
Por dentro, los circuitos se vuelven una ciudad de silicio:
pistas como avenidas, transistores como edificios, y pulsos de luz que corren por las pistas como datos.
Al final, todo el chip se enciende por zonas, la cámara sale, y cierra en un plano heroico del chip completo.
Qué debe transmitir

* Materiales creíbles: metal cepillado, silicio con reflejos iridiscentes, vidrio, cobre.
* Luz con intención: reflejos que recorren las superficies, brillo (bloom) en los pulsos, profundidad de campo en los planos cercanos.
* Escala: que se sienta el salto de "objeto en la mano" a "ciudad microscópica".
* Mucho detalle en cada plano. Nada minimalista ni vacío.

Reglas

* Solo código: geometría generada de forma procedural (nada de modelos 3D descargados),
texturas y materiales hechos con código o shaders. Sin modelos de generación de imagen, video ni audio.
* Sin marcas: que no se parezca a ningún chip, logo ni diseño real.
* Sonido: sintetízalo con código (zumbido eléctrico que sube, golpes al encenderse cada zona, pulsos de datos),
disparado por los mismos eventos que la animación, sin samples.

Formato

* 1920×1080, 60 fps, MP4 con audio.
* Si da tiempo, una versión 4K renderizada de forma nativa (no reescalada).

Cómo quiero que trabajes

* Antes de programar, propón 2–3 enfoques técnicos (por ejemplo: Three.js con postprocesado, raymarching con shaders, u otro),
elige uno y justifica por qué.
* Propón también 2–3 direcciones visuales (paleta, tipo de luz, ritmo de cámara), elige una y explica por qué.
* Renderiza frames clave de cada tramo, revísalos (legibilidad de la escala, materiales, ruido, bloom excesivo) y corrige.
* Si algo va a tardar más de ~45 min, avísame antes y propón una versión más simple.
* Escribe un `DECISIONES.md` con:
   * técnica y flujo técnico,
   * las opciones que propusiste, cuál elegiste y qué descartaste y por qué,
   * cómo generaste la geometría, los materiales y la luz,
   * cómo sincronizaste el sonido,
   * iteraciones y correcciones,
   * tiempo total y tiempo de render.
