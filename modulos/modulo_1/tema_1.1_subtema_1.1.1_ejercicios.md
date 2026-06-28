# Ejercicios: Security by Design y Defense in Depth

## Ejercicio 1. Análisis de Arquitectura

**Contexto**: Estás diseñando una API para un banco.
**Tarea**: Identifica al menos 3 capas de defensa (Defense in Depth) que aplicarías para proteger el endpoint de transferencias `POST /api/transfers`.

1. **Capa 1 (Red)**: **\*\*\*\***\_\_**\*\*\*\***
2. **Capa 2 (Aplicación)**: **\*\*\*\***\_\_**\*\*\*\***
3. **Capa 3 (Datos)**: **\*\*\*\***\_\_**\*\*\*\***

## Ejercicio 2: Refactorización hacia "Security by Design"

El siguiente código viola el principio de "Menor Privilegio" y "Valores por Defecto Seguros". Propón una corrección.

```csharp
public void ConfigureServices(IServiceCollection services)
{
    // Habilita todo para desarrollo fácil
    services.AddControllers().AddJsonOptions(opts => opts.JsonSerializerOptions.IncludeFields = true);

    // Conexión con usuario 'sa' (System admin)
    services.AddDbContext<AppDbContext>(options =>
        options.UseSqlServer("Server=.;Database=BankDb;User Id=sa;Password=superadmin;"));
}
```

**Tu Solución**:

---
