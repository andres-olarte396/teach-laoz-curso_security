# La Tríada CIA: Confidencialidad, Integridad y Disponibilidad

## 1. Introducción

La **CIA Triad** es el modelo base de la seguridad de la información. No se trata de la agencia de inteligencia, sino de tres pilares que deben equilibrarse en cualquier sistema .NET seguro.

1. **Confidencialidad (Confidentiality)**: Solo los autorizados ven los datos.
2. **Integridad (Integrity)**: Los datos no han sido alterados indebidamente.
3. **Disponibilidad (Availability)**: El sistema está accesible cuando se necesita.

## 2. Aplicación en .NET

### Confidencialidad

Garantizamos que los datos sensibles (PII, tarjetas de crédito, secretos comerciales) estén protegidos contra accesos no autorizados.

* **En Transito**: Usar siempre HTTPS (TLS 1.2+).
* **En Reposo**: Encriptación de base de datos (TDE en SQL Server) o de columnas específicas.
* **En Código**: Evitar *Hardcoded Secrets*. Usar Azure Key Vault o User Secrets.

```csharp
// Malo: Exponer datos sensibles en logs
_logger.LogInformation("Procesando pago para tarjeta: {Tarjeta}", tarjetaNumero);

// Bueno: Enmascarar o no loguear
_logger.LogInformation("Procesando pago para tarjeta terminada en: {Ultimos4}", tarjetaNumero.Substring(12));
```

### Integridad

Aseguramos que los datos son fiables y no han sido manipulados por un atacante o error del sistema.

* **Hashing**: Almacenar contraseñas con algoritmos robustos (PBKDF2, Argon2) usando ASP.NET Core Identity.
* **Firmas Digitales**: Verificar que un archivo o mensaje proviene de una fuente confiable.
* **Transactions**: Usar transacciones de base de datos para evitar estados inconsistentes parciales.

### Disponibilidad

El sistema debe resistir ataques de denegación de servicio (DoS) y fallos de infraestructura.

* **Rate Limiting**: Limitar peticiones por IP en .NET 7+.
* **Redundancia**: Desplegar múltiples instancias de la API detrás de un Load Balancer.
* **Backups**: Procedimientos de recuperación ante desastres.

```csharp
// Ejemplo de Rate Limiting en Program.cs
builder.Services.AddRateLimiter(options => {
    options.GlobalLimiter = PartitionedRateLimiter.Create<HttpContext, string>(context =>
        RateLimitPartition.GetFixedWindowLimiter(
            partitionKey: context.Connection.RemoteIpAddress?.ToString() ?? "anon",
            factory: partition => new FixedWindowRateLimiterOptions
            {
                AutoReplenishment = true,
                PermitLimit = 10,
                QueueLimit = 0,
                Window = TimeSpan.FromSeconds(5)
            }));
});
```

## 3. El Equilibrio (Trade-offs)

Maximizar uno puede afectar a los otros.

* Un sistema ultra-seguro (Alta Confidencialidad) podría ser lento o difícil de usar (Baja Disponibilidad).
* Un sistema con backups constantes (Alta Disponibilidad) podría exponer más copias de datos (Riesgo de Confidencialidad).

El trabajo del arquitecto .NET es encontrar el balance adecuado según el negocio.
