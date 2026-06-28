# Secure Code Review (Revisión de Código Seguro)

## 1. El Ojo Humano vs. La Máquina

Las herramientas automatizadas (SAST) encuentran patrones conocidos, pero la revisión humana encuentra fallos de lógica de negocio que ninguna herramienta puede detectar.

* **SAST**: Encuentra "SQL Injection en la línea 40".
* **Humano**: Encuentra "¿Por qué este usuario puede aprobar sus propios gastos?".

## 2. Checklist de Revisión Segura para .NET

Al revisar un Pull Request (PR), busca:

### Validación de Entrada

* ¿Todos los inputs públicos se validan? (Length, Type, Range, Format).
* ¿Se usa `ModelState.IsValid` en los controladores?

### Autenticación y Autorización

* ¿El endpoint privado tiene el atributo `[Authorize]`?
* ¿Se verifican roles o claims específicos?
* ¿Se chequea que el recurso (ID) pertenezca al usuario actual? (IDOR).

### Manejo de Datos

* ¿Hay secretos (connection strings, keys) hardcodeados?
* ¿Se están logueando datos sensibles (PII)?
* ¿Se usa Entity Framework o parámetros para SQL?

### Criptografía

* ¿Se usa criptografía aprobada? (AES-256, SHA-256, Argon2).
* ¿Se están generando números aleatorios seguros? (`RandomNumberGenerator` vs `Random`).

## 3. Cultura de Seguridad

La seguridad no debe ser un bloqueo o un regaño.

* **No culpes**: "El código tiene un fallo", no "Tú fallaste".
* **Educa**: "Usa X en lugar de Y porque..."
* **Bloquea constructivamente**: No apruebes un PR inseguro, pero ofrece la solución.
