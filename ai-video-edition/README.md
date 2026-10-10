# 🎬 AI Video Edition — Template Setup

Guía rápida para inicializar tu entorno de edición de video con código y Remotion.

> 📺 **Video de referencia en YouTube:** [Ver tutorial en el canal](https://youtu.be/oTcHfkKvOJc)

---

## 📋 Orden de Uso y Configuración

Sigue estos pasos antes de pedirle a la IA que cree el proyecto:

### 1. Revisa la configuración base
- Abre [CONFIG.md](file:///Users/hantroid/Desktop/Hans/hans-recursos/ai-video-edition/CONFIG.md) para entender el alcance completo del proyecto, las herramientas que se instalarán y el flujo de trabajo automatizado.

### 2. Personaliza tu estilo visual
- Abre [ESTILO.md](file:///Users/hantroid/Desktop/Hans/hans-recursos/ai-video-edition/ESTILO.md) y adáptalo a la identidad visual de tu canal o marca:
  - **Paleta de colores:** Modifica los valores hexadecimales y asignaciones de acento.
  - **Tipografía:** Selecciona tus fuentes (Google Fonts) y escalas de tamaño.
  - **Espaciados y formas:** Ajusta márgenes, radios de esquinas y proporciones de paneles.
  - **Modos visuales:** Añade o quita modos según tu formato de contenido.

### 3. Sincroniza la sección de estilo en CONFIG
- Si hiciste cambios importantes en `ESTILO.md`, actualiza la **Sección 3 ("ESTILO.md — la dirección visual")** dentro de [CONFIG.md](file:///Users/hantroid/Desktop/Hans/hans-recursos/ai-video-edition/CONFIG.md) para que el prompt maestro contenga exactamente tus reglas de diseño.

### 4. Ejecuta el Setup con la IA
- Copia y pega el contenido completo de [CONFIG.md](file:///Users/hantroid/Desktop/Hans/hans-recursos/ai-video-edition/CONFIG.md) como instrucción para tu asistente de IA (o indícale que ejecute las instrucciones contenidas en `CONFIG.md`).
- La IA construirá el proyecto de forma 100% autónoma y local (instalación de dependencias, scripts de ingesta, tokens de diseño, primitivas de Remotion y prueba end-to-end).

---

## 📁 Archivos Clave

| Archivo | Propósito |
|---|---|
| [README.md](file:///Users/hantroid/Desktop/Hans/hans-recursos/ai-video-edition/README.md) | Guía de uso y pasos de inicialización. |
| [ESTILO.md](file:///Users/hantroid/Desktop/Hans/hans-recursos/ai-video-edition/ESTILO.md) | Dirección de arte, paleta, tipografías, ritmo y reglas visuales. |
| [CONFIG.md](file:///Users/hantroid/Desktop/Hans/hans-recursos/ai-video-edition/CONFIG.md) | Prompt maestro autónomo para crear el proyecto desde cero. |
