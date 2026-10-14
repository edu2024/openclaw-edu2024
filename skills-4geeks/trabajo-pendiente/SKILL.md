---
name: trabajo-pendiente
description: Indica qué tareas o asignaciones de 4Geeks aún deben completarse.
---

# Skill: trabajo pendiente

## Cuándo usar
Cuando se pregunte qué tareas o asignaciones están pendientes de completar o
entregar en el curso.

## Prerrequisitos
- Tener configurado el secreto `FOURGEEKS_TOKEN` en el almacén de secretos de
  OpenClaw.
- Usar el token mediante el mecanismo seguro de ejecución del Gateway; nunca
  mostrar su valor.
- Seguir las reglas aplicables de `AGENTS.md`.

## Procedimiento
1. Llamar a
   `GET /v1/assignment/user/me/task?task_status=PENDING`
   con la cabecera `Authorization: Token $FOURGEEKS_TOKEN`.
2. Contar las tareas pendientes y devolver el total.
3. Si se pide el detalle, listar título y tipo (proyecto, ejercicio, lección)
   de las pendientes; si son muchas, resumir el conteo por tipo.
4. No mostrar datos personales ni el token.

## Salida esperada
El total de tareas pendientes y, si corresponde, el desglose por tipo o la
lista corta, indicando que aún deben completarse.

## Casos especiales
- Si la API responde HTTP 401, informar que el token no fue aceptado.
- Distinguir entre tarea pendiente de hacer y pendiente de corrección; usar el
  estado real que devuelve la API.