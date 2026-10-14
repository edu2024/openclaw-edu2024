---
name: mi-avance
description: Resume cuánto llevo hecho del curso: avance, progreso, cuánto falta y cómo voy.
---

# Skill: mi avance

## Cuándo usar
Cuando se pregunte cómo voy en el curso, cuánto llevo hecho, cuánto falta o el
porcentaje de proyectos entregados.

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
2. Contar el total de proyectos asignados.
3. Contar cuántos tienen `task_status` en `DONE`.
4. Contar cuántos tienen `revision_status` distinto de `PENDING`.
5. Devolver los tres números y el porcentaje de entregados
   (`entregados / total * 100`). No volcar la lista completa.

## Salida esperada
Tres números (total, entregados, corregidos) y el porcentaje de entregados. El
total coincide con los proyectos asignados y el número de entregados nunca
supera el total.

## Casos especiales
- Entregado y corregido son campos distintos: una tarea entregada puede estar
  sin corregir.
- Si la API no responde, indicar en qué paso se cortó y no inventar números.
- Si la API responde HTTP 401, informar que el token no fue aceptado.