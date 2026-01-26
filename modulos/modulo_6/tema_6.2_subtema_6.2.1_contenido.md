# Pruebas de Seguridad en APIs (OWASP API Top 10)

## 1. El OWASP API Security Top 10 (2023)

Las APIs tienen riesgos únicos que las aplicaciones web tradicionales no tienen.
OWASP creó una lista específica para esto.

### Riesgos Clave

1. **API1:2023 - Broken Object Level Authorization (BOLA)**: El rey de las vulnerabilidades API.
    * Yo soy User 1. Pido `GET /api/invoices/5`. La factura 5 es del User 2. La API me la da.
    * También conocido como IDOR (Insecure Direct Object Reference).
2. **API2:2023 - Broken Authentication**: Tokens mal implementados, sin rotación, passwords débiles.
3. **API3:2023 - Broken Object Property Level Authorization**: Mass Label Assignment.
    * Envío `POST /api/users { "name": "Me", "role": "admin" }`. La API sobrescribe mi rol ciegamente.
4. **API4:2023 - Unrestricted Resource Consumption**: DoS application-layer.
    * No hay rate limiting. Un usuario pide 1 millón de registros de una vez.

## 2. Cómo probar BOLA (IDOR)

Es difícil de automatizar porque el scanner no sabe qué dato pertenece a qué usuario. Requiere lógica de negocio.

* **Prueba Manual**:
    1. Logueate como Usuario A. Obtén el ID de un recurso suyo (ID: 100).
    2. Logueate como Usuario B.
    3. Intenta acceder a `GET /api/resource/100` con el token del Usuario B.
    4. Si devuelve 200 OK -> **VULNERABLE**.
    5. Si devuelve 403 Forbidden / 404 Not Found -> **SEGURO**.

## 3. Mass Assignment

En .NET, prevenimos esto usando **DTOs (Data Transfer Objects)** en lugar de exponer las Entidades de EF Core directamente en el controlador.

* **Mal**: `public ActionResult Update(User user)` -> El binder mapea todo, incluso `Roles`.
* **Bien**: `public ActionResult Update(UpdateUserDto dto)` -> El DTO solo tiene `Name` y `Email`.

## 4. Conclusión

La seguridad de APIs requiere pensar en "Objetos" y "Propiedades", no solo en páginas.
Use DTOs. Valide IDs. Limite el consumo.
