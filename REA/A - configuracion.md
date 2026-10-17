Prepara este proyecto para usar REA (Reverse Engineer Anything) sobre una app de Mac. Sigue este checklist en orden, marca cada punto con ✅ o ❌ y no avances si uno falla sin decirme por qué:

1. **Node:** REA pide Node 22.19 o superior (o 24.11+). Revisa mi versión. Si es vieja, actualízala con nvm (si no tengo nvm, instálalo desde github.com/nvm-sh/nvm): carga nvm con `source ~/.nvm/nvm.sh`, luego `nvm install 24` y `nvm alias default 24`. Si tengo otro Node instalado (instalador oficial o Homebrew), revisa cuál queda primero en el PATH de una terminal nueva y, si sigue ganando el viejo, dime exactamente qué hacer.
2. **REA:** instálalo solo desde la fuente oficial (paquete de npm `rea-agents`, repo github.com/morluto/rea) con `npx rea-agents@latest setup`, usando el Node nuevo. Elige Claude Code y explícame cada cambio antes de aceptarlo. Si el setup hace preguntas interactivas que no puedes contestar desde aquí, dame el comando exacto para correrlo en mi terminal.
3. **Hopper** (para analizar apps nativas): acepta que el setup lo instale en modo demo. Luego ábrelo una vez y avísame, porque la ventana de "demo o licencia" la tengo que cerrar yo.
4. **Revisa que el MCP de REA va a arrancar con el Node nuevo** (mira con qué comando quedó registrado) y no con el viejo.
5. **Herramientas para después:** confirma que tengo FFmpeg y Python 3.11. Si falta alguno, instálalo con Homebrew.

Al final dame la tabla del checklist y dime que reinicie Claude Code para que cargue REA.
