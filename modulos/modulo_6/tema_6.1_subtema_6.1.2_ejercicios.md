# Ejercicios: Burp y Automatización

## Ejercicio: Burp Repeater

Capturas una petición GET a `/api/products/10`.
La envías al Repeater.
Cambias el 10 por `-1` y envías.
El servidor responde con un Stack Trace gigante de .NET que muestra la ruta del archivo en disco `C:\Inetpub\wwwroot\...`.

¿Qué vulnerabilidad acabas de confirmar?

1. SQL Injection.
2. Improper Error Handling (Information Disclosure).
3. XSS.

**Respuesta**: ____________________

## Ejercicio: Test de Seguridad

Completa el test para verificar que un usuario normal NO puede borrar usuarios.

```csharp
[Fact]
public async Task DeleteUser_AsNormalUser_ReturnsForbidden()
{
    // Arrange
    var client = _factory.CreateClientWithUserToken(); // Usuario normal
    
    // Act
    var response = await client.DeleteAsync("/api/users/5");
    
    // Assert
    Assert.Equal(HttpStatusCode._______, response.StatusCode); // ¿Qué código esperamos?
}
```

**Respuesta**: HttpStatusCode.__________ (Forbidden o Unauthorized?)
