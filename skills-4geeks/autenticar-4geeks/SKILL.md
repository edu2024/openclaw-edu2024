---
name: autenticar-4geeks
description: Verifica que el token de 4Geeks sea aceptado consultando el perfil de admisiones.
---

# Skill: autenticar 4Geeks

## Cuándo usar
Cuando se necesite confirmar que el token `FOURGEEKS_TOKEN` es válido antes de
usar cualquier otra habilidad, o cuando se pregunte quién es el usuario en la
plataforma de 4Geeks.

## Prerrequisitos
- Tener configurado el secreto `FOURGEEKS_TOKEN` en el almacén de secretos de
  OpenClaw.
- Usar el token mediante el mecanismo seguro de ejecución del Gateway; nunca
  mostrar su valor.
- Seguir las reglas aplicables de `AGENTS.md`.

## Procedimiento
1. Llamar a `GET /v1/admissions/user/me` con la cabecera
   `Authorization: Token $FOURGEEKS_TOKEN` (el secreto se resuelve en `exec`).
2. Interpretar el código HTTP:
   - HTTP 200: el token es válido. Devolver solo el nombre, correo y academias
     enlazadas (`profile_academy`); no mostrar datos innecesarios.
   - HTTP 401: el token no fue aceptado. Informar y sugerir revisar el secreto.
3. No imprimir el token ni la respuesta completa si contiene datos personales.

## Salida esperada
Confirmación de que la autenticación funciona (HTTP 200) con un resumen breve
del perfil, o un aviso claro de fallo. El token nunca se muestra.

## Casos especiales
- Si el secreto no está disponible o el comando no puede resolverlo, decirlo
  explícitamente en lugar de asumir que funciona.
- No guardar el valor del token en ningún archivo de este repositorio.