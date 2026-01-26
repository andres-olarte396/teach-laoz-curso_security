# Ejercicios: API Security

## Ejercicio: Identificando BOLA

Analiza este controlador:

```csharp
[HttpGet("{id}")]
[Authorize]
public IActionResult GetOrder(int id)
{
    var order = _dbContext.Orders.Find(id);
    return Ok(order);
}
```

¿Es vulnerable a BOLA?

* [ ] No, tiene `[Authorize]`.
* [x] Sí, verifica que el usuario esté logueado, pero NO verifica que la orden `id` pertenezca a ese usuario. Cualquier usuario logueado puede ver cualquier orden.

**Corrección**:

```csharp
var userId = User.FindFirst(ClaimTypes.NameIdentifier).Value;
var order = _dbContext.Orders.FirstOrDefault(o => o.Id == id && o.UserId == userId);
if (order == null) return NotFound();
```

## Ejercicio: Mass Assignment

Tienes una clase `Product` con un campo `Price`.
Tu método de actualización recibe `Product` directamente.
Un usuario envía JSON `{"Id": 1, "Name": "Laptop", "Price": 0.01}`.
¿Qué pasa?

* El precio se actualiza a 1 centavo si no hay validación adicional.

¿Cómo lo arreglas con un DTO?
Crea una clase `UpdateProductDto` que solo tenga:

1. __________
2. __________

(Y excluya `Price`).

**Respuesta**: Name, Description (por ejemplo).
