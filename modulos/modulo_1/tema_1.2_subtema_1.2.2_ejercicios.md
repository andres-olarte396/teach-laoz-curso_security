# Ejercicios: Tipos de Ataques

## Ejercicio 1. SQL Injection

Analiza el siguiente código vulnerable:

```csharp
public User GetUser(string email) {
    string sql = $"SELECT * FROM Users WHERE Email = '{email}'";
    // ... ejecutar sql ...
}
```

Si un atacante envía como email: `admin@site.com' --`, ¿cuál es la consulta final que ejecuta la base de datos?

**Consulta Resultante**: _____________________________________________________
**Efecto**: __________________________________________________________________

## Ejercicio 2: XSS

Estás revisando una vista Razor (`Index.cshtml`). Encuentras la siguiente línea:

```html
<div>@Html.Raw(Model.UserBio)</div>
```

¿Por qué es esto peligroso si `UserBio` viene de un input de usuario?
¿Cómo lo corregirías?

**Respuesta**: _______________________________________________________________

## Ejercicio 3: CSRF

Estás creando un formulario HTML puro (sin TagHelpers de .NET) para hacer un POST a tu API. ¿Qué elemento oculto te falta incluir para que el servidor no rechace la petición por falta de token Anti-Forgery?

**Respuesta**: Un campo `input` de tipo `hidden` con el nombre `__________________` y el valor del token.
