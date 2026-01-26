# Gestión de Secretos y Configuración Segura

## 1. El Problema de los Secretos

Las cadenas de conexión, API Keys y certificados no deben estar en tu repositorio de Git. Nunca.
Si subes un secreto a GitHub, asume que está comprometido en segundos (hay bots escaneando).

## 2. Desarrollo Local: User Secrets

.NET ofrece la herramienta **User Secrets**.

* Almacena los secretos en una carpeta fuera del proyecto (en `%APPDATA%`), vinculado por un ID en el `.csproj`.
* El proveedor de configuración de .NET los lee automáticamente en entorno `Development`.

```bash
dotnet user-secrets init
dotnet user-secrets set "ConnectionStrings:MyDb" "Server=...;Password=supersecret"
```

## 3. Producción: Azure Key Vault (o equivalentes)

En producción, no usas User Secrets ni variables de entorno planas si puedes evitarlo.
Usas un servicio de gestión de secretos centralizado.

* **Azure Key Vault**: Guarda claves criptográficas y secretos.
* **Managed Identity**: Tu aplicación se autentica contra Key Vault usando su propia identidad en Azure, ¡sin necesitar una contraseña para acceder a la contraseña!

```csharp
// Program.cs
if (app.Environment.IsProduction())
{
    builder.Configuration.AddAzureKeyVault(
        new Uri("https://myvault.vault.azure.net/"),
        new DefaultAzureCredential());
}
```

## 4. AppSettings.json

* Usa este archivo para configuración **NO sensible** (URLs de servicios, flags de características).
* No pongas passwords aquí, incluso si el repo es privado.
