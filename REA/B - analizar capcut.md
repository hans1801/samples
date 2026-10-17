Usa REA para entender cómo funciona CapCut por dentro. La app está en `/Applications/CapCut.app` y la tengo instalada legalmente. Quiero analizar cómo funciona para inspirarme y construir mi propio editor. Con evidencia (archivo, función o texto que lo pruebe), averigua:
1. De qué está hecha (frameworks, motor de interfaz, navegador embebido).
2. Cómo guarda un proyecto. Ejemplo real: `~/Movies/CapCut/User Data/Projects/com.lveditor.draft/[NOMBRE_DE_UN_PROYECTO_TUYO]/draft_info.json`. Explica pistas, segmentos, materiales, unidades de tiempo, transiciones, volumen y separación de audio.
3. Cómo funcionan cortar, separar el audio, la transición "Mix", los fundidos de audio, el cambio de velocidad y exportar solo un tramo.
4. Dónde corre cada función Pro, en mi Mac o en la nube: mejorar calidad, reducir ruido de imagen, deflicker, reducir ruido de voz, mejorar voz y normalizar volumen. Si corre en la nube, solo puedes ver lo que sale de mi Mac (qué se envía y adónde), no el algoritmo: dilo así y no lo adivines.
5. Una tabla final **"Qué se pudo revisar y qué no"**, con tres columnas: la parte o función, el estado (✅ confirmado con evidencia / 🟡 parcial / ❌ no se puede ver) y el motivo (por ejemplo: corre en la nube, archivo cifrado, modelo en formato propio).

Reglas: prefiere el análisis estático y pregúntame antes de ejecutar CapCut. No uses código, modelos ni assets de CapCut, no descifres archivos cifrados ni te saltes protecciones, y si ves tokens o claves escribe `[oculto]`. Guarda todo en `informe-capcut.md`, con una sección final "Plan para MyEditor" (formato de proyecto JSON y qué hace FFmpeg en cada acción).

Cuando termines, muéstrame en el chat: un resumen corto de cada uno de los puntos 1 a 4 (2 o 3 líneas por punto, con la evidencia más clara), los 3 hallazgos más sorprendentes y la tabla "Qué se pudo revisar y qué no". No construyas nada todavía.
