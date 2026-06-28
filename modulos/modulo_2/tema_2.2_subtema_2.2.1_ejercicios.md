# Ejercicios: Revisión de Código

## Ejercicio: Encuentra el fallo (Code Review)

Revisa el siguiente fragmento de código de un controlador .NET y marca al menos 2 problemas de seguridad basándote en el Checklist.

```csharp
[HttpGet] // 1. ¿Falta Authorize?
public IActionResult GetInvoice(int id)
{
    // 2. ¿Se valida que el 'id' pertenezca al usuario?
    var invoice = _context.Invoices.Find(id);
    
    if (invoice == null) return NotFound();
    
    // 3. ¿Loguear todo el objeto invoice expone datos sensibles?
    _logger.LogInformation("Factura consultada: " + JsonSerializer.Serialize(invoice));
    
    return Ok(invoice);
}
```

**Tus hallazgos**:

1. _____________________________________________________________
2. _____________________________________________________________

## Ejercicio: Random vs Secure Random

¿Cuál de estos dos códigos usarías para generar un token de recuperación de contraseña y por qué?

**A**: `var token = new Random().Next(1000, 9999).ToString();`
**B**: `var token = Convert.ToBase64String(RandomNumberGenerator.GetBytes(32));`

**Respuesta**: Usaría la opción ____ porque...
