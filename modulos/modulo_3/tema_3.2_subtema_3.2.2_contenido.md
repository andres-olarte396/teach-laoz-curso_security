# Validación de Entrada y Cabeceras Seguras

## 1. Validación de Entrada

"Nunca confíes en el input del usuario".
Validar no es solo por UX, es la primera defensa contra ataques de Inyección.

### DataAnnotations vs FluentValidation

* **DataAnnotations**: `[Required]`, `[StringLength]`. Bueno para cosas simples.
* **FluentValidation**: Librería externa estándar en .NET. Separa la lógica de validación de los modelos.

```csharp
public class UserValidator : AbstractValidator<User> {
    public UserValidator() {
        RuleFor(x => x.Email).NotEmpty().EmailAddress();
        RuleFor(x => x.Age).InclusiveBetween(18, 99);
    }
}
```

## 2. Cabeceras de Seguridad (Security Headers)

Son instrucciones que el servidor envía al navegador para endurecer la seguridad del cliente.

### HSTS (HTTP Strict Transport Security)

Fuerza al navegador a usar siempre HTTPS, incluso si el usuario escribe `http://`.

```csharp
app.UseHsts();
```

### CSP (Content Security Policy)

Evita XSS definiendo de dónde se pueden cargar recursos (scripts, estilos, imágenes).
"Solo permite scripts de mi dominio y de Google Analytics".

* En .NET se configura añadiendo un Middleware que inyecte el header `Content-Security-Policy`.

### X-Content-Type-Options: nosniff

Evita que el navegador "adivine" el tipo de archivo (MIME sniffing), previniendo que un archivo subido como `.jpg` se ejecute como `.html`.

## 3. Ejemplo de Middleware de Cabeceras

```csharp
app.Use(async (context, next) =>
{
    context.Response.Headers.Add("X-Content-Type-Options", "nosniff");
    context.Response.Headers.Add("X-Frame-Options", "DENY"); // Evita Clickjacking
    await next();
});
```
