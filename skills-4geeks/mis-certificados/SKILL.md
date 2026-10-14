---
name: mis-certificados
description: Lista los certificados obtenidos por el usuario en 4Geeks.
---

# Skill: mis certificados

## Cuándo usar
Cuando se pregunte por los certificados obtenidos en 4Geeks, su cantidad o su
detalle.

## Prerrequisitos
- Tener configurado el secreto `FOURGEEKS_TOKEN` en el almacén de secretos de
  OpenClaw.
- Usar el token mediante el mecanismo seguro de ejecución del Gateway; nunca
  mostrar su valor.
- Seguir las reglas aplicables de `AGENTS.md`.

## Procedimiento
1. Llamar a `GET /v1/certificate/` con la cabecera
   `Authorization: Token $FOURGEEKS_TOKEN`.
2. Si se pide de un cohort concreto, añadir `cohort` (id).
3. Devolver la cantidad de certificados y, si se pide, su lista breve
   (nombre o token de certificado público), sin exponer datos personales.
4. Si la API responde HTTP 401, informar que el token no fue aceptado y no
   inventar certificados.

## Salida esperada
El número de certificados obtenidos (y el detalle si se solicita), confirmando
que proviene de la API de certificados. El token nunca se muestra.

## Casos especiales
- Los enlaces públicos de certificado usan el token del certificado; compartir
  solo por canales seguros si el usuario lo pide.
- Mantener esta skill enfocada en obtener/listar certificados, sin incluir
  otras acciones de la API.