# Monitoreo, Logging y SIEM

## 1. Si no lo ves, no pasó (Logging)

El registro de eventos es la "caja negra" del avión.
Pero cuidado: **Loguear demasiado es tan malo como no loguear**.

* NO loguear PII (Emails, Tarjetas, Passwords).
* SÍ loguear eventos de seguridad (Login fallido, Acceso denegado, Cambio de rol).

## 2. SIEM (Security Information and Event Management)

Un archivo de texto en el servidor no sirve de mucho.
Necesitas centralizar los logs de:

* La aplicación .NET
* El Firewall (FortiGate)
* El Servidor Web (IIS/Nginx)
* La Base de Datos

El **SIEM** (como **FortiAnalyzer** o **Azure Sentinel**) correlaciona estos eventos.
"Alguien intentó loguearse 50 veces fallidas en la API (Log App) desde una IP en Rusia (Log Firewall), y luego esa misma IP intentó acceder a la base de datos (Log DB)". -> **ALERTA ROJA**.

## 3. Implementación en .NET (Serilog)

Usar Serilog para escribir logs estructurados (JSON) que el SIEM pueda entender.

```csharp
Log.Logger = new LoggerConfiguration()
    .WriteTo.Console()
    .WriteTo.Seq("http://localhost:5341") // Centralizador
    .CreateLogger();

// Uso
_logger.LogWarning("Seguridad: Intento de acceso no autorizado al recurso {RecursoId} por usuario {Usuario}", id, User.Identity.Name);
```
