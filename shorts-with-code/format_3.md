Crea una animación en **Remotion** para una serie de videos titulada **«La palabra del día es…»**.

El video debe tener formato **vertical 9:16 (1080 × 1920)** y cuatro escenas con voz en off:

### Escena 1: Introducción
- **Voz en off:** «La palabra del día es…».
- **Visual:** Muestra distintas palabras que cambian rápidamente, como una ruleta de texto. Sincroniza la animación con la narración y prepara la transición hacia la palabra elegida.

### Escena 2: La palabra
- **Voz en off:** Pronuncia la palabra elegida.
- **Visual:** Revela la palabra en grande, centrada y con una animación que le dé protagonismo.

### Escena 3: Definición
- **Voz en off:** Lee una definición breve, clara y fácil de entender.
- **Visual:** Muestra exactamente la definición narrada. Puedes destacar términos clave y revelar el texto por frases, manteniendo suficiente tiempo para leerlo.

### Escena 4: Ejemplo
- **Voz en off:** Lee una oración que ejemplifique el uso de la palabra.
- **Visual:** Muestra exactamente el ejemplo narrado y resalta la palabra elegida dentro de la oración.

### Estilo y ritmo
- Usa un diseño limpio, tipografía grande, buen contraste y márgenes seguros para visualizarlo en móviles.
- Mantén una identidad visual coherente y transiciones fluidas entre escenas.
- Ajusta la duración de cada escena al audio, con pausas naturales. Evita cortar la narración o retirar el texto demasiado pronto.

### Generación de voz
- Genera la narración mediante la API de **Voice Box**, disponible en `http://127.0.0.1:17493`.
- Utiliza la voz cuyo nombre exacto es **«My voice»** en las cuatro escenas.
- Comprueba cómo funciona la API antes de integrarla; no inventes rutas ni parámetros.
- Si la API o la voz no están disponibles, indícamelo antes de usar una alternativa.

### Flujo de trabajo
1. Si no te he indicado una palabra, propón una para este primer video.
2. Primero presenta las **cuatro escenas** en una tabla con: texto exacto de la voz en off, texto en pantalla, animación propuesta y duración estimada.
3. **Espera mi confirmación antes de generar los audios, programar la animación o renderizar el video.**
4. Tras mi aprobación, crea la animación, sincroniza los elementos con la voz en off y entrega el video final en MP4.