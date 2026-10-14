---
name: mi-actividad
description: Consulta la actividad de aprendizaje del usuario en la plataforma de 4Geeks.
---

# Skill: mi actividad

## Cuándo usar
Cuando se pregunte por la actividad reciente de aprendizaje: tiempo dedicado,
ejercicios realizados o movimiento en el curso.

## Prerrequisitos
- Tener configurado el secreto `FOURGEEKS_TOKEN` en el almacén de secretos de
  OpenClaw.
- Usar el token mediante el mecanismo seguro de ejecución del Gateway; nunca
  mostrar su valor.
- Seguir las reglas aplicables de `AGENTS.md`.

## Procedimiento
1. Llamar a `GET /v1/activity/me` con la cabecera
   `Authorization: Token $FOURGEEKS_TOKEN`.
2. Si se pide actividad de un período, añadir `date_start` y `date_end`
   (formato `YYYY-MM-DD`); si se pide de un cohort, añadir `cohort`.
3. Resumir lo relevante: tiempo de actividad, ejercicios realizados o rango de
   fechas consultado, sin volcar datos personales.
4. Si la API responde HTTP 401, informar que el token no fue aceptado y no
   inventar actividad.

## Salida esperada
Un resumen breve de la actividad de aprendizaje devuelta por la API, con el
rango de fechas o cohort usado. El token nunca se muestra.

## Casos especiales
- Si no se especifica período, usar el rango que la API devuelva por defecto.
- No mezclar esta consulta con otras habilidades: una sola preocupación por
  skill.