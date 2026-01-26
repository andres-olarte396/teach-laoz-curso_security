# Ejercicios: Implementando Defensas

## Ejercicio: Reparando una Redirección Insegura

Tienes este controlador de Login:

```csharp
[HttpPost]
public IActionResult Login(LoginModel model, string returnUrl)
{
    if (_authService.Validate(model))
    {
        // INSEGURO
        return Redirect(returnUrl); 
    }
    return View(model);
}
```

Escribe la versión corregida que evite ataques de Open Redirect:

```csharp
[HttpPost]
public IActionResult Login(LoginModel model, string returnUrl)
{
    if (_authService.Validate(model))
    {
        // CORREGIDO:
        // _________________________________________________
        // _________________________________________________
    }
    return View(model);
}
```

## Ejercicio: Configuración de Cookies

¿Qué propiedad de la Cookie impide que un script malicioso (XSS) pueda robar el token de sesión?

* [ ] `SameSite=Strict`
* [ ] `Secure`
* [ ] `HttpOnly`

**Respuesta**: ______________________
