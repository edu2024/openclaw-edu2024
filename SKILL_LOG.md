# Registro de skills 4Geeks

Las skills se crearon conversando con OpenClaw desde la TUI. Las pruebas autenticadas están pendientes; no se afirma que hayan sido exitosas.

| Skill | Prompt/propósito | Endpoint | Evidencia de prueba |
|---|---|---|---|
| `autenticar-4geeks` | Consultar el perfil de admisiones usando el secreto `FOURGEEKS_TOKEN`, sin revelar su valor. | `GET https://breathecode.herokuapp.com/v1/admissions/user/me` | Pendiente; no se hizo una llamada autenticada. |
| `mis-proyectos` | Listar mis proyectos de 4Geeks usando el secreto `FOURGEEKS_TOKEN`. | `GET https://breathecode.herokuapp.com/v1/assignment/user/me/task?task_type=PROJECT` | Pendiente; no se hizo una llamada autenticada. |
| `trabajo-pendiente` | Listar tareas pendientes usando el secreto `FOURGEEKS_TOKEN`. | `GET https://breathecode.herokuapp.com/v1/assignment/user/me/task?task_status=PENDING` | Pendiente; no se hizo una llamada autenticada. |
| `mi-avance` | Contar proyectos totales y proyectos con `task_status=DONE`, y calcular el porcentaje entregado, sin mostrar la lista completa. | `GET https://breathecode.herokuapp.com/v1/assignment/user/me/task?task_type=PROJECT` | Pendiente; no se hizo una llamada autenticada. |
| `mi-actividad` | Consultar mi actividad de aprendizaje usando el secreto `FOURGEEKS_TOKEN`. | `GET https://breathecode.herokuapp.com/v1/activity/me` | Pendiente; no se hizo una llamada autenticada. |
| `mis-certificados` | Listar mis certificados usando el secreto `FOURGEEKS_TOKEN`. | `GET https://breathecode.herokuapp.com/v1/certificate/` | Pendiente; no se hizo una llamada autenticada. |

## Seguridad y limitaciones

El secreto `FOURGEEKS_TOKEN` se guardó en el almacén de secretos de OpenClaw y no se incluye en este registro. No se realizaron llamadas autenticadas porque la instalación no tenía disponible un mecanismo aprobado para usar el secreto en una petición sin exponerlo.

La referencia de BreatheCode indica autenticación mediante la cabecera `Authorization: Token <token>`. Las pruebas quedan pendientes de poder ejecutarse de forma segura.
