# Ejercicios: Autenticación y JWT

## Ejercicio: Análisis de Token JWT

Ve a [jwt.io](https://jwt.io) y pega el siguiente token (ficticio, no seguro) para ver qué hay dentro.

`eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyLCJyb2xlIjoiQWRtaW4ifQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c`

1. ¿Cuál es el algoritmo de firma (`alg`)? __________________
2. ¿Qué rol tiene el usuario? __________________
3. ¿Podría cambiar el rol a "SuperAdmin" y que la API lo acepte si no tengo la clave privada?
    * [ ] Sí
    * [ ] No (La firma fallaría)

## Ejercicio: Configuración de Identity

Estás configurando las reglas de password para tu empresa.
Escribe el código C# para:

* Mínimo 12 caracteres.
* Requerir al menos un dígito.
* Requerir mayúsculas y minúsculas.

```csharp
builder.Services.Configure<IdentityOptions>(options =>
{
    options.Password.RequiredLength = ____;
    options.Password.RequireDigit = ____;
    options.Password.RequireLowercase = ____;
    options.Password.RequireUppercase = ____;
});
```
