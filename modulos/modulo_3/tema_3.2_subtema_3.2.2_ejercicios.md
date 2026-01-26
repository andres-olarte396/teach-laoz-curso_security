# Ejercicios: Validación y Cabeceras

## Ejercicio: Reglas de Validación

Usando FluentValidation, escribe una regla para un campo `Password` que:

1. No sea vacío.
2. Tenga mínimo 8 caracteres.
3. Contenga la palabra "seguro" (solo por el ejemplo).

```csharp
RuleFor(x => x.Password)
    .______()
    .MinimumLength(____)
    .Must(p => p.Contains("______"));
```

## Ejercicio: Cabeceras

Relaciona la cabecera con su función:

1. `Strict-Transport-Security` (HSTS)
2. `X-Frame-Options: DENY`
3. `Content-Security-Policy`

* ( ) Evita que tu sitio sea cargado dentro de un `<iframe>` (protege contra Clickjacking).
* ( ) Obliga al navegador a usar HTTPS en el futuro.
* ( ) Define una lista blanca de fuentes de contenido permitidas.

**Solución**:
1 -> __, 2 ->__, 3 -> __
