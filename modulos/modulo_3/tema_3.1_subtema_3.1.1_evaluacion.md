# Evaluación: Autenticación

### Pregunta 1

¿Cuál es la principal ventaja de usar JWT en lugar de cookies de sesión para una API distribuida (Microservicios)?

- a) Los JWT son más pequeños.
- [x] B) Los JWT son "stateless" (autocontenidos), no requieren que la API consulte una base de datos de sesiones en cada petición.
- c) Los JWT nunca caducan.

### Pregunta 2

¿Qué es un **Claim** en ASP.NET Core Identity?

- a) Una demanda legal contra el desarrollador.
- [x] B) Un par clave-valor que representa un dato sobre el usuario (ej. `Email: juan@mail.com`, `Age: 30`).
- c) Una contraseña encriptada.

### Pregunta 3

Si usas `AddDefaultTokenProviders()` en Identity, ¿qué funcionalidad obtienes?

- a) Tokens gratuitos de criptomonedas.
- [x] B) Generación de tokens para reseteo de contraseña, confirmación de email y 2FA.
- c) Tokens JWT automáticos.
