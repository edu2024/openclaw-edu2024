# Registro de skills 4Geeks

Las skills se crearon desde la TUI de OpenClaw. El secreto `FOURGEEKS_TOKEN` no se incluye en este registro. Se anotan los resultados observados, incluidos los intentos fallidos.

| Skill | Prompt/propósito | Endpoint | Evidencia de prueba |
|---|---|---|---|
| `autenticar-4geeks` | Consultar el perfil de admisiones con `FOURGEEKS_TOKEN`, sin mostrar datos personales. | `GET https://breathecode.herokuapp.com/v1/admissions/user/me` | Exitosa: HTTP 200. |
| `mis-proyectos` | Listar los proyectos asignados usando `FOURGEEKS_TOKEN`. | `GET https://breathecode.herokuapp.com/v1/assignment/user/me/task?task_type=PROJECT` | Exitosa: HTTP 200; devolvió 15 proyectos. |
| `trabajo-pendiente` | Listar las tareas pendientes usando `FOURGEEKS_TOKEN`. | `GET https://breathecode.herokuapp.com/v1/assignment/user/me/task?task_status=PENDING` | Exitosa: HTTP 200; devolvió 19 tareas pendientes. |
| `mi-avance` | Contar los proyectos totales y los que tienen `task_status=DONE`, y calcular el porcentaje entregado sin mostrar la lista completa. | `GET https://breathecode.herokuapp.com/v1/assignment/user/me/task?task_type=PROJECT` | Fallida: HTTP 401; no se obtuvieron métricas. |
| `mi-actividad` | Consultar la actividad de aprendizaje con `FOURGEEKS_TOKEN`. | `GET https://breathecode.herokuapp.com/v1/activity/me` | Fallida: HTTP 401; no se pudo determinar la actividad. |
| `mis-certificados` | Listar los certificados con `FOURGEEKS_TOKEN`. | `GET https://breathecode.herokuapp.com/v1/certificate/` | Fallida: HTTP 401; no se pudo determinar la cantidad. |

## Iteraciones y observaciones

- La skill `autenticar-4geeks` se ajustó para usar la cabecera `Authorization: Token` con el secreto disponible para `exec` en el Gateway. Tras actualizar el token, la prueba respondió HTTP 200.
- Las skills `mis-proyectos` y `trabajo-pendiente` respondieron HTTP 200.
- Las skills `mi-avance`, `mi-actividad` y `mis-certificados` respondieron HTTP 401; se registran como fallidas, no como pruebas exitosas.
- La referencia de BreatheCode indica autenticación mediante `Authorization: Token <token>` y confirma los endpoints y filtros usados aquí. No se afirma que `revision_status` haya sido verificado.

## Seguridad

`FOURGEEKS_TOKEN` se almacena en el almacén de secretos de OpenClaw. Su valor no se incluye en este archivo.
