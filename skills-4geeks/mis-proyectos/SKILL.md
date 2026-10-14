---
name: mis-proyectos
description: Lista los proyectos asignados en 4Geeks con su estado.
---

# Skill: mis proyectos

## Cuándo usar
Cuando se pregunten los proyectos asignados en el curso, o su estado
(pendiente, entregado, calificado).

## Prerrequisitos
- Tener configurado el secreto `FOURGEEKS_TOKEN` en el almacén de secretos de
  OpenClaw.
- Usar el token mediante el mecanismo seguro de ejecución del Gateway; nunca
  mostrar su valor.
- Seguir las reglas aplicables de `AGENTS.md`.

## Procedimiento
1. Llamar a
   `GET /v1/assignment/user/me/task?task_type=PROJECT`
   con la cabecera `Authorization: Token $FOURGEEKS_TOKEN`.
2. Devolver el total de proyectos y una lista breve con su `title` y
   `task_status` (por ejemplo, PENDING, DONE, APPROVED, REJECTED).
3. Si la lista es larga, resumir por estado en lugar de volcarla completa.
4. No mostrar datos personales ni el token.

## Salida esperada
Total de proyectos asignados y su desglose por estado (o la lista corta con
título y estado), confirmando que provienen de la API de asignaciones.

## Casos especiales
- Si la API responde HTTP 401, informar que el token no fue aceptado.
- Si un proyecto no tiene estado claro, indicarlo en lugar de inventarlo.