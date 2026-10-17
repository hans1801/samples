Lee `informe-capcut.md` y construye **"MyEditor"** a partir de ese informe, sobre todo de la sección "Plan para MyEditor". Es una app web local con Vite + React + TypeScript y un servidor Node pequeño que llame a FFmpeg. Sin nube ni cuentas. Usa diseño, nombre e íconos propios: nada del logo, los colores ni los textos de CapCut. Solo estas funciones:
1. Importar videos y audios arrastrándolos.
2. Línea de tiempo con una pista de video y una de audio, cabezal y zoom.
3. Cortar en el cabezal (tecla S), borrar un segmento y recortar los bordes.
4. Separar el audio del video en su propia pista.
5. Transición "Mix" (fundido cruzado) con duración ajustable.
6. Fundidos de entrada y salida, y volumen por segmento.
7. Exportar a MP4 (1080p o 4K) todo el proyecto o solo un tramo marcado con I y O.
8. Guardar y abrir el proyecto en JSON.

Nada de subtítulos, textos ni filtros. Para comprobar que funciona, no uses videos míos: genera dos clips de prueba con FFmpeg (por ejemplo `testsrc` con un tono de audio, de 10 s cada uno), corta, separa el audio, pon una transición Mix de 0,5 s, exporta un tramo de 5 s y revisa con `ffprobe` que dure 5 s y tenga audio. Después bórralos. La prueba real la hago yo subiendo mis videos a la app.

**Al final**, dame una tabla: qué salió del informe de REA y qué construiste a partir de eso.
