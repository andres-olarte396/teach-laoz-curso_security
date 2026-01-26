# Burp Suite y Fuzzing

## 1. Burp Suite: El Estándar Profesional

Si ZAP es la navaja suiza gratuita, **Burp Suite Professional** es el bisturí láser de pago (aunque tiene una versión Community gratuita).
Es la herramienta #1 usada por pentesters profesionales.

### Características Clave (Community Edition)

* **Proxy**: Igual que ZAP.
* **Repeater**: Capturas una petición, la envías al Repeater, modificas un byte, y la reenvías. Repites esto hasta romper la app. Es manual y muy poderoso.
* **Intruder**: Permite automatizar ataques de fuerza bruta o fuzzing (limitado en velocidad en la versión gratis).

## 2. Fuzzing (Pruebas de Fuzz)

El Fuzzing consiste en enviar datos aleatorios, inválidos o inesperados a una entrada (input) para ver cómo reacciona el sistema.
"¿Qué pasa si envío 10,000 caracteres 'A' en el campo de usuario? ¿Se cae el servidor (Buffer Overflow)?".

### Fuzzing de APIs en .NET

Podemos hacer fuzzing ligero con `Intruder` o herramientas de línea de comando como `Wfuzz` o `FFUF`.

* **Target**: `POST /api/login`
* **Payload**: Diccionario de 10,000 passwords comunes (`rockyou.txt`).
* **Condition**: Si la respuesta tiene "Longitud > 500 bytes", es un éxito.

## 3. Pruebas de Seguridad Automatizadas en APIs

Más allá del pentesting manual, podemos escribir Tests de Integración que validen seguridad.
En .NET, usando `XUnit` + `TestServer`:

```csharp
[Fact]
public async Task Get_SecureData_WithoutToken_ReturnsUnauthorized()
{
    // Arrange
    var client = _factory.CreateClient(); // Cliente sin token
    
    // Act
    var response = await client.GetAsync("/api/secure-data");
    
    // Assert
    Assert.Equal(HttpStatusCode.Unauthorized, response.StatusCode);
}
```

Esto es **regresión de seguridad**: Asegura que nadie quite el `[Authorize]` por accidente mañana.
