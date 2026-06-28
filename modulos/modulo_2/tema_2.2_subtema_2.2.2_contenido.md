# Validación de Dependencias y SBOM

## 1. El Riesgo de la Cadena de Suministro

Hoy en día, el 80-90% del código de una aplicación moderna son librerías de terceros (Open Source).
Si usas un paquete NuGet infectado, tu aplicación está infectada, por muy seguro que sea "tu" código.

## 2. SBOM (Software Bill Of Materials)

Es como una lista de ingredientes de tu software.

* Lista todos los componentes, versiones, y licencias usadas en tu proyecto.
* Es esencial para saber si estás afectado cuando sale una vulnerabilidad crítica (ej. Log4j).

**Herramientas en .NET**:

* `CycloneDX`: Un estándar y herramienta para generar SBOMs.

## 3. Escaneo de Vulnerabilidades (SCA)

Software Composition Analysis (SCA) es el proceso de verificar si tus dependencias tienen vulnerabilidades conocidas (CVEs).

### dotnet list package --vulnerable

El comando nativo de .NET CLI.

```bash
dotnet list package --vulnerable --include-transitive
```

### OWASP Dependency Check

Una herramienta clásica que cruza tus DLLs contra la base de datos nacional de vulnerabilidades (NVD).

## 4. Gestión de Riesgos

Cuando encuentras una vulnerabilidad:

1. **Actualizar**: A la versión parcheada (lo ideal).
2. **Mitigar**: Si no puedes actualizar, aplica controles compensatorios (ej. deshabilitar la funcionalidad afectada).
3. **Aceptar**: Si el riesgo es bajo y no hay fix, documenta la excepción (temporalmente).
