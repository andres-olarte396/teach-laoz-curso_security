# Tipos de Ataques Comunes

## 1. Introducción

Más allá de las categorías abstractas de OWASP, es vital entender cómo funcionan los ataques específicos a nivel técnico para poder prevenirlos en .NET.

## 2. Inyección SQL (SQL Injection)

Ocurre cuando datos no confiables se concatenan directamente en una consulta SQL.
**Impacto**: Robo de datos, modificación de registros, bypass de autenticación.

```csharp
// VULNERABLE:
var query = "SELECT * FROM Users WHERE Name = '" + userName + "'";

// SEGURO (Entity Framework Core):
var user = context.Users.FirstOrDefault(u => u.Name == userName);
// SEGURO (ADO.NET con Parámetros):
var cmd = new SqlCommand("SELECT * FROM Users WHERE Name = @Name", conn);
cmd.Parameters.AddWithValue("@Name", userName);
```

## 3. Cross-Site Scripting (XSS)

El atacante inyecta scripts maliciosos (Javascript) en páginas vistas por otros usuarios.
**Impacto**: Robo de cookies de sesión, redirección a sitios de phishing.

* **Reflected XSS**: El script viene en la URL.
* **Stored XSS**: El script se guarda en la BD y se muestra a todos (ej. en un comentario de foro).

**Mitigación en .NET**: Razor encodea HTML por defecto (`@Variable`). Ten cuidado con `Html.Raw()`.

## 4. Cross-Site Request Forgery (CSRF)

El atacante engaña al navegador de la víctima para que ejecute una acción no deseada en un sitio donde la víctima está logueada.
**Ejemplo**: Un link oculto que hace POST a `/bank/transfer?amount=1000&to=Attacker`.

**Mitigación en .NET**: Usar Anti-Forgery Tokens.

```csharp
app.UseRouting();
app.UseAuthentication();
app.UseAuthorization();
// Middleware que valida tokens CSRF
app.MapControllers(); 
```

Y en los formularios Razor: `@Html.AntiForgeryToken()` (o automático en ASP.NET Core).

## 5. Denegación de Servicio (DoS)

Intentar saturar el servidor para que no pueda atender a usuarios legítimos.
**Mitigación**: Rate Limiting, caching, y validación de tamaño de inputs.
