# Evaluación: Tipos de Ataques

### Pregunta 1

El uso de `SqlCommand` con `Parameters.AddWithValue()` es la defensa principal contra:

- [x] A) SQL Injection
- b) XSS
- c) CSRF

> **Respuesta Correcta:** A) SQL Injection
>
> **Justificación:** Al proteger la disponibilidad del servicio, evitando que se caiga o se sobrecargue sin autorización.

### Pregunta 2

¿Qué ataque aprovecha la confianza del servidor en el navegador del usuario (y sus cookies) para ejecutar acciones no autorizadas?

- a) XSS
- b) CSRF (Cross-Site Request Forgery)
- c) Man-in-the-Middle

> **Respuesta Correcta:** B) CSRF (Cross-Site Request Forgery)
>
> **Justificación:** Al proteger la disponibilidad del servicio, evitando que se caiga o se sobrecargue sin autorización.

### Pregunta 3

Si usas `@Html.Raw()` en una vista Razor con datos provenientes de la base de datos sin sanitizar, estás exponiendo tu sitio a:

- a) SQL Injection
- b) Stored XSS
- c) Reflected XSS

> **Respuesta Correcta:** b) Stored XSS
>
> **Justificación:**
