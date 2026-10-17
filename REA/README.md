# 🔍 REA (Reverse Engineer Anything) — Recrear CapCut con IA

Colección de prompts utilizados en el video para investigar aplicaciones mediante ingeniería inversa con **REA** (servidor MCP) y **Claude Code**, construyendo un editor de video local a medida.

> 📺 **Video en YouTube:** [Ver tutorial completo en el canal](https://youtube.com/@hansacha)

---

## 📋 Flujo de Trabajo y Orden de Uso

Ejecuta los prompts en este orden dentro de tu agente de IA (como Claude Code):

| Paso | Archivo | Propósito |
|---|---|---|
| **1** | [A - configuracion.md](A%20-%20configuracion.md) | Valida Node (22.19+ / 24+), instala el servidor MCP oficial de REA, Hopper en modo demo y verifica el entorno. |
| **2** | [B - analizar capcut.md](B%20-%20analizar%20capcut.md) | Usa REA para analizar la app local, inspeccionar binarios con Hopper y generar el informe técnico con límites local vs. nube. |
| **3** | [C - construir myeditor.md](C%20-%20construir%20myeditor.md) | Lee el informe y construye una app web local (Vite + React + TS + FFmpeg) con timeline, cortes, pistas de audio y exportación. |
| **4** | [D - mejoras pro.md](D%20-%20mejoras%20pro.md) | Agrega mejoras avanzadas 100% locales: reducción de ruido, calidad de rostro con GFPGAN v1.4 y mejora de voz con Resemble Enhance. |

---

## ⚠️ Requisitos previos
- **Node.js:** Versión 22.19+ o 24.11+
- **Agente de IA compatible con MCP:** Claude Code, Cursor o Codex
- **Herramientas de sistema:** FFmpeg y Python 3.11 (para las mejoras de audio/imagen)
