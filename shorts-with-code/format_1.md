Actúa como un desarrollador Senior de videojuegos Web y HTML5 experto en físicas 2D y diseño retro. Necesito que generes un archivo único `index.html` (con HTML, CSS y JavaScript integrados) que recree una versión altamente fiel y jugable del Nivel 1-1 de Super Mario Bros.

**Especificaciones del juego:**

1. **Controles:**
   * **A / D:** Mover a Mario a la izquierda y derecha.
   * **W / Barra Espaciadora:** Saltar (soporte para salto variable: a mayor tiempo presionada la tecla, más alto salta).
   * Controles fluidos con inercia, aceleración y desaceleración rápida para imitar la física clásica de Mario.

2. **Audio y Sonidos (Audio API nativo / Sintetizado):**
   * Incorpora efectos de sonido generados por código (usando Web Audio API para no depender de archivos externos que puedan romper la carga):
     * Sonido de salto.
     * Sonido al golpear bloques `?` / romper ladrillos.
     * Sonido al pisar un Goomba.
     * Sonido de muerte (caer a un foso o tocar un enemigo).
     * Melodía o Jingle al tocar la bandera final.

3. **Físicas y Lógica del Nivel 1-1:**
   * **Gravedad y Colisiones:** Detección de colisiones precisas (AABB) por arriba, abajo y laterales.
   * **Cámara de Scroll Horizontal:** La pantalla sigue a Mario al avanzar a la derecha (sin permitir volver atrás, como en el juego original).
   * **Elementos del Mapa:**
     * Suelo marrón tradicional con agujeros/fosos mortales.
     * Bloques `?` (que sueltan monedas o se vuelven grises al golpearse desde abajo) y bloques de ladrillo rompibles.
     * Tuberías verdes clásicas de diferentes alturas actuando como obstáculos sólidos.
     * Poste de bandera al final del nivel para detectar la victoria.

4. **Enemigos e Interacciones:**
   * **Goombas:** Enemigos con movimiento horizontal autónomo.
   * Si Mario salta encima del Goomba, este se aplasta y desaparece con sonido.
   * Si el Goomba toca a Mario lateralmente, Mario pierde, suena el audio de muerte y el nivel se reinicia.

5. **Gráficos e Interfaz (UI):**
   * Renderizado en `<canvas>` de HTML5 con dimensiones retro adaptadas (ej. 800x400 px), centrado y estilizado con CSS.
   * Marcador superior en pantalla con datos estilo arcade: `MARIO`, `PUNTOS`, `MONEDAS`, `WORLD 1-1` y `TIEMPO`.
   * Sprites pixel-art dibujados por código en canvas o representaciones geométricas detalladas muy reconocibles.

6. **Entrega del código:**
   * Debe ser un único documento `<!DOCTYPE html>` funcional, listo para guardar y ejecutar en cualquier navegador moderno sin requerir servidores ni dependencias externas.