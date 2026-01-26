# Evaluación: Defensas Web

### Pregunta 1

¿Por qué `Redirect()` es potencialmente peligroso si se usa con un input de usuario no validado?

- [x] A) Permite ataques de Open Redirect (redirigir a sitios de phishing).
- b) Consume mucha memoria.
- c) Bloquea el navegador.

### Pregunta 2

¿Cómo protege Razor contra XSS por defecto?

- a) Eliminando todas las etiquetas HTML.
- [x] B) Codificando (encoding) los caracteres especiales (ej. `<` se vuelve `&lt;`) antes de renderizar.
- c) Encriptando el HTML.

### Pregunta 3

Si usas `FromSqlRaw` en Entity Framework Core, ¿estás protegido automáticamente contra SQL Injection?

- a) Sí, siempre.
- [x] B) No, si concatenas strings manualmente dentro del método. Debes usar parámetros o `FromSqlInterpolated`.
