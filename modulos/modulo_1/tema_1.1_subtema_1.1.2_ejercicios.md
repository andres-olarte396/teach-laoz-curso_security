# Ejercicios: La Tríada CIA

## Ejercicio 1. Clasificación de Incidentes

Clasifica los siguientes eventos según qué pilar de la CIA ha sido comprometido:

1. Un ataque de Ransomware cifra todos los archivos del servidor y pide rescate.
    * **Pilar afectado**: ______________________
2. Un empleado descontento modifica los registros de nómina para aumentarse el sueldo.
    * **Pilar afectado**: ______________________
3. Un hacker intercepta el tráfico Wi-Fi y roba las cookies de sesión de los usuarios.
    * **Pilar afectado**: ______________________

## Ejercicio 2: Implementación en Código

**Objetivo**: Proteger la **Confidencialidad** de una cadena de conexión.

El siguiente código lee la conexión directamente del código fuente:

```csharp
var connectionString = "Server=myServerAddress;Database=myDataBase;User Id=myUsername;Password=mySecretPassword;";
builder.Services.AddDbContext<MyContext>(options => options.UseSqlServer(connectionString));
```

**Tarea**: Escribe cómo modificarías este código para leer la configuración de manera segura usando el sistema de configuración de .NET (`IConfiguration`).

**Solución**:

```csharp
// Escribe tu código aquí
```
