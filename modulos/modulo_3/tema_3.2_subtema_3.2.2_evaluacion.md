# Evaluación: Validación y Headers

### Pregunta 1

¿Qué hace la cabecera HSTS?

- a) Encripta el tráfico HTTP.
- [x] B) Le dice al navegador que recuerde usar SOLO HTTPS para este dominio por un tiempo determinado (ej. 1 año).
- c) Redirige al usuario a la página de login.

### Pregunta 2

Estás validando un modelo de entrada. ¿Dónde es el MEJOR lugar para hacerlo?

- a) Solo en el Frontend (Javascript) para que sea rápido.
- b) Solo en la base de datos (Constraints).
- [x] C) En el Backend (API/Controller), independientemente de si ya se validó en el frontend. La validación del backend es la única en la que puedes confiar.

### Pregunta 3

`X-Frame-Options: DENY` ayuda a prevenir:

- a) SQL Injection
- [x] B) Clickjacking (Montar tu sitio en un iframe invisible para robar clics)
- c) XSS
