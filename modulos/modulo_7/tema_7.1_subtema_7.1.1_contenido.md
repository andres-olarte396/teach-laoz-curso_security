# Estandarización y Guías de Seguridad

## 1. Si no está escrito, no existe

La seguridad no puede depender de la memoria de los desarrolladores. Necesita ser codificada:

1. **Guías escritas**: Documentación (Wiki).
2. **Guías automatizadas**: Linters y reglas de IDE (.editorconfig).

## 2. EditorConfig y Roslyn Analyzers

En .NET, podemos forzar reglas de estilo y calidad directamente en el IDE.
Si creas un archivo `.editorconfig` en la raíz, defines reglas como:

```ini
[*.cs]
# Forzar el uso de var (Estilo)
csharp_style_var_for_built_in_types = true:warning

# Reglas de Seguridad (vía NuGet Roslynator o SonarAnalyzer)
dotnet_diagnostic.S3649.severity = error # SQL Injection
```

## 3. Guía de "Secure Coding"

Debes crear un documento `SECURE_CODING.md` en tu repositorio que explique:

* ¿Cómo validamos inputs aquí? (FluentValidation).
* ¿Cómo manejamos excepciones? (No mostrar StackTrace).
* ¿Cómo logueamos? (Sin datos sensibles).
* ¿Cómo autenticamos? (Identity Server).

Esto acelera el onboarding de nuevos devs y reduce errores recurrentes.
