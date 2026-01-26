# Ejercicios: Gestión de Secretos

## Ejercicio: Comandos de User Secrets

Ordena los pasos para iniciar el uso de secretos en un proyecto nuevo:

1. `dotnet user-secrets set "ApiKey" "12345"`
2. `dotnet user-secrets init`
3. Instalar el paquete NuGet `Microsoft.Extensions.Configuration.UserSecrets` (si no viene incluído).

**Orden Correcto**: ___,___, ___

## Ejercicio: Identificación de Riesgos

Revisas un repositorio y encuentras este archivo `appsettings.json`:

```json
{
  "Logging": { "LogLevel": { "Default": "Information" } },
  "Stripe": {
    "PublishableKey": "pk_test_12345",
    "SecretKey": "sk_live_987654321" 
  }
}
```

¿Qué está mal aquí?

* [ ] La Publishable Key es visible.
* [ ] La SecretKey (de producción 'live') está commiteada en el archivo.
* [ ] El nivel de log es Information.

**Respuesta**: __________________________________________________
