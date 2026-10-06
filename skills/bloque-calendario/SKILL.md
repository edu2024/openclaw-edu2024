---
name: bloque-calendario
description: Crea en Google Calendar un evento descrito en lenguaje natural.
---

# Skill: bloque de calendario

## Cuándo usar
Cuando Dante pida crear o agendar un evento en Google Calendar.

## Prerrequisitos
- Usar únicamente las herramientas de Google Calendar ya disponibles mediante Zapier MCP.
- Seguir las reglas aplicables de `AGENTS.md` y el contexto de `USER.md`.
- No solicitar ni configurar nuevas API keys, conexiones OAuth o integraciones.

## Procedimiento
1. Identificar el título o propósito, la fecha, la hora de inicio y la duración.
2. Si falta un dato necesario o la fecha/hora es ambigua, preguntar antes de crear el evento. Usar la zona horaria y el calendario predeterminados de la cuenta, si están configurados; si no, confirmar cuál usar.
3. Crear el evento mediante la herramienta de Google Calendar disponible. Añadir recordatorio solo si Dante lo solicita o lo especifica.
4. No afirmar que se creó hasta recibir confirmación de la herramienta. Si falla, informar claramente y no repetir la operación a ciegas.
5. Tras confirmar la creación, responder en español y de forma concisa con el título, fecha, hora y enlace o identificador disponible.

## Salida esperada
Existe un evento en el calendario acordado con los datos confirmados, y Rayo informa el resultado sin inventar detalles.

## Casos especiales
- Si Dante no confirma los datos necesarios, no crear el evento.
- No crear eventos duplicados para una misma solicitud.
