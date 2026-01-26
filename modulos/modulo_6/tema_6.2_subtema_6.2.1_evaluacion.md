# Evaluación: API Security

### Pregunta 1

¿Qué vulnerabilidad describe mejor el escenario: "Un usuario puede acceder a los datos privados de otro usuario simplemente cambiando el ID en la URL"?

- a) SQL Injection.
- [x] B) BOLA (Broken Object Level Authorization) / IDOR.
- c) XSS.

### Pregunta 2

¿Cuál es la mejor defensa contra Mass Assignment (Asignación Masiva)?

- a) Usar `[Authorize]`.
- [x] B) Usar DTOs (Data Transfer Objects) para definir exactamente qué campos pueden ser enviados por el cliente, en lugar de usar las entidades de base de datos directamente.
- c) Usar HTTPS.

### Pregunta 3

La vulnerabilidad "Unrestricted Resource Consumption" (Consumo de recursos sin restricciones) se mitiga principalmente con:

- a) Rate Limiting y Paginación.
- b) Firewalls.
- c) Antivirus.
- [x] A) Rate Limiting (limitar peticiones) y Paginación (no devolver 1 millón de filas).
