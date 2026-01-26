# Implementación de Defensas Web

## 1. Protección contra XSS (Cross-Site Scripting)

ASP.NET Core usa **Razor** como motor de vistas. Razor codifica automáticamente cualquier salida (`@Model.Texto`), convirtiendo `<script>` en `&lt;script&gt;`.

* **Peligro**: Uso de `Html.Raw()`, `PutHtml()` o concatenación manual de strings en APIs.
* **Solución**: Usar siempre los mecanismos de codificación por defecto.

## 2. Protección contra CSRF (Cross-Site Request Forgery)

Para aplicaciones MVC/Razor Pages, ASP.NET incluye **Anti-Forgery Tokens** automáticamente en los formularios creados con Tag Helpers.

* **En APIs**: Se suelen omitir si se usa autenticación basada en JWT (Authorization Header) y almacenamiento en LocalStorage, ya que el navegador no envía estos headers automáticamente (a diferencia de las cookies).
* **Si usas Cookies con API**: Debes implementar `SameSite=Strict` en tus cookies.

```csharp
// Configuración de Cookie segura
services.ConfigureApplicationCookie(options => {
    options.Cookie.HttpOnly = true; // No accesible por JS
    options.Cookie.SecurePolicy = CookieSecurePolicy.Always; // Solo HTTPS
    options.Cookie.SameSite = SameSiteMode.Strict; // Solo desde el mismo origen
});
```

## 3. Protección contra SQL Injection

Usar **Entity Framework Core** es la mejor defensa.
EF Core usa consultas parametrizadas internamente.

* **Peligro**: `FromSqlRaw("SELECT * FROM Users WHERE Name = '" + name + "'")`.
* **Solución**: `FromSqlInterpolated($"SELECT * FROM Users WHERE Name = {name}")` (EF Core lo convierte en parámetro).

## 4. Protección contra Redirección Abierta (Open Redirect)

Un atacante engaña al usuario con un link `mi-sitio.com/login?returnUrl=sitio-malicioso.com`.
Si tu código hace `Redirect(returnUrl)` sin validar, el usuario confiará y caerá en la trampa.

* **Solución**: Usar `LocalRedirect(returnUrl)` o verificar `Url.IsLocalUrl(returnUrl)`.
