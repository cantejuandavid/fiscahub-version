# Privacidad en solicitudes web

- Nunca incluir información personal del usuario (correo electrónico, nombre, usuario, identificadores, ubicación, tokens personales) en encabezados (headers), URL, parámetros de consulta ni cuerpo de solicitudes HTTP/HTTPS (GET, POST u otras) hacia servicios externos.
- Esto aplica a curl, wget, scripts, WebFetch, WebSearch y cualquier otra herramienta.
- No establecer encabezados como `From`, `User-Agent` personalizados con datos del usuario, ni `Authorization`/cookies con credenciales personales, salvo que el usuario lo pida explícitamente para esa solicitud concreta.
