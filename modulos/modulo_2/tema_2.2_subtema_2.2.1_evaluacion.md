# Evaluación: Code Review

### Pregunta 1

¿Qué tipo de vulnerabilidad es más probable que detecte un revisor humano y se le escape a una herramienta SAST automática?

- a) Un SQL Injection simple.
- [x] B) Un fallo en la lógica de negocio (ej. un usuario aprobando su propia solicitud).
- c) Una librería desactualizada.

### Pregunta 2

Al revisar un controlador API, notas que falta el atributo `[Authorize]`. ¿Qué riesgo implica esto?

- [x] A) Cualquier usuario (incluso anónimo) podría ejecutar esa acción.
- b) El código será más lento.
- c) No se podrá debuggear.

### Pregunta 3

¿Por qué `System.Random` NO es seguro para generar contraseñas o tokens?

- a) Porque genera números muy grandes.
- [x] B) Porque es predecible (pseudo-aleatorio basado en el reloj).
- c) Porque el compilador lo optimiza.
