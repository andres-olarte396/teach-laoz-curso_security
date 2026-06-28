# Security by Design y Defense in Depth

## 1. Introducción

En el desarrollo de software moderno, la seguridad no puede ser una "capa" que se añade al final del proyecto. **Security by Design** (Seguridad por Diseño) y **Defense in Depth** (Defensa en Profundidad) son dos filosofías fundamentales que transforman cómo construimos aplicaciones en .NET.

## 2. Security by Design

Este principio establece que el software debe ser diseñado para ser seguro desde sus cimientos.

### Principios Clave

1. **Minimización de la Superficie de Ataque**: Exponer solo lo estrictamente necesario.
2. **Principio de Menor Privilegio**: Cada componente o usuario debe tener solo los permisos necesarios para realizar su función.
3. **Valores por Defecto Seguros**: La configuración inicial debe ser la más restrictiva.

> **Ejemplo en .NET**:
> En lugar de abrir todos los puertos en Kestrel y permitir cualquier origen en CORS, configuramos explícitamente solo los dominios confiables.

```csharp
// Inseguro (Permissive)
app.UseCors(builder => builder.AllowAnyOrigin());

// Seguro (Security by Design)
app.UseCors(builder => builder.WithOrigins("https://mi-empresa.com"));
```

## 3. Defense in Depth (Defensa en Profundidad)

Es una estrategia de seguridad que utiliza múltiples capas de defensa para proteger la integridad de la información. Si una capa falla, las otras siguen protegiendo.

### Capas habituales en una aplicación .NET

1. **Perímetro**: Firewalls, WAF (Web Application Firewall).
2. **Red**: Segmentación, VNets Azure.
3. **Host**: Parches del SO, Contenedores seguros.
4. **Aplicación**: Autenticación, Validación de Inputs (nuestro foco).
5. **Datos**: Encriptación (Encryption at Rest/Transit).

## 4. Comparativa

| Concepto | Enfoque | Metáfora |
| :--- | :--- | :--- |
| **Security by Design** | Proactivo (Planeación) | Un edificio con cimientos antisísmicos. |
| **Defense in Depth** | Reactivo/Redundante (Capas) | Un castillo con foso, muralla y guardia. |

## 5. Conclusión

Aplicar estos conceptos en .NET implica usar las herramientas del framework (Identity, DataProtection) no como accesorios, sino como piezas centrales de la arquitectura.
