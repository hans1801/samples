Hook isométrico: "La ciudad que se enciende"
Objetivo
Animación de 12 segundos, 16:9, para abrir un vídeo de motion design.
Un diorama isométrico de una calle de noche que pasa de la oscuridad total a estar
llena de luz, encendiéndose a ritmo de la música. Debe atrapar en el primer segundo.
Técnica (obligatoria, igual que el proyecto ../claude-aniamtions)

* Node.js + @napi-rs/canvas (Skia) para dibujar cada fotograma con código.
* ffmpeg para codificar; render en paralelo por tramos.
* Audio sintetizado en JavaScript propio (osciladores, ruido, envolventes, reverb).
* Cada fotograma es función pura del tiempo (determinista), así que los tramos empalman.
* Cero imágenes, audios, modelos o fuentes descargadas (solo fuentes del sistema).
* Puedes reutilizar ideas de ../claude-aniamtions (proyección isométrica, primitivas
box/cyl/plane, timeline de eventos, síntesis de audio, build.sh).

Escena: una calle en miniatura sobre una base de diorama

* Calle empedrada mojada con charcos que reflejan las luces.
* Tres fachadas: cafetería (toldo, mesitas, cafetera que humea), librería (escaparate
con libros), tienda de discos (vinilo girando en el escaparate).
* Farolas de hierro, un tranvía que cruza, cables eléctricos entre edificios,
ropa tendida, macetas en los balcones, un gato en un tejado, un buzón, una bici apoyada.
* Lluvia fina constante, con salpicaduras en los charcos.
* Letreros de neón en español ("CAFÉ", "LIBROS", "DISCOS") que parpadean al encenderse.

Guion (sincronizado a 100 BPM, 0,6 s por pulso)

* 0,0–1,2 · Negro casi total: solo se intuye la silueta de la calle con la lluvia.
Un rayo ilumina todo durante un instante (fogonazo blanco, trueno sintetizado);
se ve la calle entera un segundo y vuelve la oscuridad.
* 1,2–7,0 · Encendido a ritmo, una luz por pulso, con cadena visual:
farola 1 → farola 2 → escaparate de la cafetería → neón "CAFÉ" (parpadea y fija)
→ ventanas de arriba una tras otra → librería → neón "LIBROS" → tienda de discos
→ neón "DISCOS" → guirnalda de bombillas entre edificios (se enciende en cascada).
Cada luz: halo aditivo, luz que cae sobre las paredes y el suelo, y su reflejo
temblando en los charcos.
* 7,0–10,0 · La calle cobra vida: cruza el tranvía con chispas en el cable, el gato
se despierta y camina por el tejado, sale vapor de la cafetera, el vinilo gira,
una persona con paraguas cruza. Cámara: acercamiento lento con leve órbita.
* 10,0–12,0 · Plano general, toda la calle encendida. Título "TU TÍTULO AQUÍ" que
aparece como otro neón más (parpadeo + zumbido) y golpe final. Corte a negro.

Calidad visual (lo más importante)

* Luz como protagonista: oscuridad azul profunda frente a luces cálidas (ámbar, rosa,
cian en los neones). Usa composición aditiva para halos y multiplicación para sombras.
* Reflejos en el suelo mojado: las luces se duplican invertidas y onduladas en los charcos.
* Iluminación coherente: cada luz encendida aclara su zona de pared y suelo (máscaras
de degradado radial), y las zonas sin luz se quedan oscuras.
* Detalle denso: ninguna zona vacía; ladrillos, tejas, macetas, carteles, cables.
* Easing con carácter, overshoot y escalonado (stagger) en todo lo que aparece.
* Textos de los neones perfectamente legibles.

Sonido (100 % sintetizado con código, desde los mismos eventos que la animación)

* Lluvia constante (ruido filtrado), trueno al inicio.
* Cada luz que se enciende = un "clic" eléctrico + una nota de una escala, que forman
una melodía ascendente; los neones con zumbido y parpadeo audible.
* Música lo-fi a 100 BPM que entra después del trueno; tranvía con campanita.
* Entrega el MP4 con audio mezclado y, aparte, la música y los efectos en WAV.

Formato

* Solo 16:9: 1920×1080, 30 fps, MP4, 12 segundos.

Cómo quiero que trabajes

1. Muéstrame el plan: mapa de pulsos (qué se enciende en cada pulso) y textos.
2. Todo desde un `data.json` (BPM, orden de encendido, colores de cada luz).
3. Renderiza frames clave (oscuro, a mitad del encendido, final) y una hoja de contactos;
revísalos y corrige lo que se vea plano, vacío o ilegible.
4. Escribe un `DECISIONES.md` corto con técnicas, iteraciones y tiempo total.
Límite: el render no debe tardar más de unos minutos.
