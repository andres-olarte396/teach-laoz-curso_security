# Evaluación: Fundamentos de Seguridad

## Analiza el siguiente escenario

Un desarrollador decide encriptar las contraseñas en la base de datos (Capa de Datos), pero permite que la API sea accesible vía HTTP sin certificado SSL (Capa de Transporte).

### Pregunta 1

¿Qué principio de seguridad se está violando principalmente?

- a) Security by Design (Valores por defecto seguros)
- b) Defense in Depth (Falla en una capa crítica anula la otra)
- c) Principio de Menor Privilegio

> **Respuesta Correcta:** B) Defense in Depth.
>
> **Justificación:** Defense in Depth (Al fallar la capa de transporte, la capa de datos es irrelevante si se intercepta antes)

### Pregunta 2

Security by Design implica:

- a) Contratar un equipo de pentesting al final del proyecto.
- b) Considerar requisitos de seguridad desde la toma de requerimientos y diseño.
- c) Usar la librería de seguridad más cara del mercado.

> **Respuesta Correcta:** B) Considerar requisitos de seguridad desde la toma de requerimientos y diseño.
>
> **Justificación:** Considerar requisitos de seguridad desde la toma de requerimientos y diseño.
