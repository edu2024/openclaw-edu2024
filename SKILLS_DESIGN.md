# Diseño de skills

## 1. nota-en-drive

1. **¿Qué hace?** Guarda una nota o resumen como documento editable en Google Drive.
2. **¿Qué input necesita?** El texto que quiero guardar. Si falta, Rayo pregunta antes de crear el documento. Rayo usa mis convenciones de `USER.md` y `TOOLS.md`: responde en español, es conciso, nombra el archivo `PMO-YYYY-MM-DD — título` y lo guarda en la carpeta `Agente`.
3. **¿Cómo es un buen output?** Un documento creado en la carpeta `Agente`, con ese formato de nombre, y Rayo devuelve el enlace. Si no logra crearlo, lo indica sin afirmar que se creó.

## 2. bloque-calendario

1. **¿Qué hace?** Crea en Google Calendar un evento descrito en lenguaje natural.
2. **¿Qué input necesita?** El título o propósito, fecha, hora de inicio y duración. Si falta algún dato necesario, Rayo pregunta antes de crear el evento y utiliza la zona horaria y el calendario predeterminados configurados para la cuenta.
3. **¿Cómo es un buen output?** Un evento creado con los datos acordados y Rayo confirma el título, fecha y hora, compartiendo el enlace o identificador disponible. Si la creación falla, lo indica claramente.
