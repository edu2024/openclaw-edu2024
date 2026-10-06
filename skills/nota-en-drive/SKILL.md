---
name: nota-en-drive
description: Guarda una nota o resumen como documento editable en Google Drive.
---

# Skill: nota en Drive

## Cuándo usar
Cuando Dante pida guardar una nota, idea o resumen en Google Drive.

## Prerrequisitos
- Usar únicamente las herramientas de Google Drive que ya están disponibles mediante Zapier MCP.
- Seguir las convenciones de `TOOLS.md` y las reglas aplicables de `AGENTS.md`.
- No solicitar ni configurar nuevas API keys, conexiones OAuth o integraciones.

## Procedimiento
1. Si el texto que se quiere guardar no está incluido, preguntar qué contenido debe guardarse. Si está vacío, no crear nada.
2. Preparar un título breve y fiel al contenido, con este formato:
   `PMO-YYYY-MM-DD — título`
   Usar la fecha actual y no inventar datos.
3. Crear un documento editable en Google Drive, dentro de la carpeta `Agente`, mediante la herramienta de Zapier MCP disponible para crear archivos desde texto. Si la herramienta permite conversión a documento de Google, activarla.
4. No asumir que el documento se creó hasta recibir confirmación de la herramienta. Si la carpeta no se puede identificar o la creación falla, informar a Dante y no afirmar que tuvo éxito.
5. Cuando se confirme la creación, devolver el nombre y el enlace disponible al documento.

## Salida esperada
Existe un documento editable en la carpeta `Agente`, su nombre comienza con `PMO-` y la fecha actual, y Rayo devuelve el enlace.

## Casos especiales
- Si falta información necesaria, preguntar antes de crear.
- No sobrescribir ni reemplazar documentos existentes; crear uno nuevo.
