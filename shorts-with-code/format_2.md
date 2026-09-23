```
# Prompt para Claude: Efecto Parallax de Paisaje (Día a Noche con GSAP)

Copia y pega el siguiente bloque directamente en Claude para generar el proyecto completo:

---

```markdown
Actúa como un desarrollador frontend senior especializado en Creative Coding y animaciones web interactivas con GSAP.

Necesito que desarrolles una experiencia web inmersiva de scroll vertical utilizando HTML5, CSS3 moderno y GSAP (GreenSock Animation Platform) con el plugin ScrollTrigger. La escena debe representar un paisaje que transiciona visualmente desde el atardecer/día hasta la noche conforme el usuario hace scroll.

### Requisitos Técnicos y de Diseño:

1. **Estructura y Composición (HTML / SVG):**
   - Implementa un contenedor de desplazamiento de altura extendida (ej. `min-height: 450vh`) para dar suficiente recorrido a la animación.
   - Crea un viewport fijo (`position: sticky` o `position: fixed`) de `100vw` y `100vh` que contenga las capas ordenadas en el eje Z:
     - **Capa 1 (Fondo):** Cielo dinámico con gradiente.
     - **Capa 2 (Astros):** Sol que desciende y Luna/estrellas que emergen.
     - **Capa 3 (Profundidad lejana):** Silueta o vectores de montañas distantes.
     - **Capa 4 (Profundidad media):** Montañas cercanas y colinas con tonalidad intermedia.
     - **Capa 5 (Primer plano):** Siluetas de árboles/bosque y bandada de aves con trayectorias curvas.
     - **Capa 6 (Overlay UI/Texto):** Títulos o tarjetas de contenido tipográfico que aparecen y se desvanecen con blur (`filter: blur(...)`) y opacidad en momentos clave.
   - Puedes usar vectores SVG inline limpios para las siluetas o fondos CSS bien estructurados para que el ejemplo sea 100% autocontenido y listo para ejecutar.

2. **Estilos y Performance (CSS):**
   - Usa variables CSS para paletas de color diurna y nocturna.
   - Aplica `will-change: transform` y transformaciones 3D (`translate3d`) para asegurar un renderizado a 60 FPS por GPU sin repaints costosos.
   - Diseño completamente responsive adaptable a mobile y desktop.

3. **Lógica de Animación (JavaScript + GSAP ScrollTrigger):**
   - Registra e inicializa `ScrollTrigger`.
   - Crea una `gsap.timeline()` central con `scrollTrigger`:
     - `trigger`: Contenedor principal.
     - `start`: `"top top"`.
     - `end`: `"bottom bottom"`.
     - `scrub`: `1.5` o `2` (para suavizado inercial elástico).
   - **Transición cromática del cielo:** Interpolar de un atardecer vibrante (`#ff7e5f`, `#feb47b`) a un anochecer profundo/estelar (`#0b0c10`, `#1f2833`).
   - **Trayectoria celeste:** El Sol debe descender y ocultarse tras las montañas mientras la Luna y un campo de estrellas ganan opacidad.
   - **Paralaje multicapa:** Asigna multiplicadores de velocidad diferenciados a cada capa (más lento en el fondo, más rápido en el primer plano).

4. **Entrega esperada:**
   - Código modular separado en 3 bloques claros: HTML, CSS y JS.
   - CDN de GSAP 3 y ScrollTrigger listos para incluir.
   - Breves notas explicativas sobre cómo ajustar la fricción del `scrub`, añadir marcadores (`markers: true`) para depuración y calibrar el `z-index`.
```

---

### Consejos de Ajuste Rápido
* **Scrub:** Un valor numérico (ej. `1.5` o `2`) añade inercia y suavidad. `scrub: true` sincroniza estrictamente 1:1 con la rueda del ratón.
* **Pinning:** Si prefieres fijar la escena sin capas `fixed`, puedes usar `pin: true` dentro de la configuración de `scrollTrigger`.
```