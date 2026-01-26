# Ejercicios: Configurando Calidad

## Ejercicio: Definiendo un Quality Gate

Tu equipo decide ser estricto con la seguridad pero laxo con los tests unitarios al principio.
Diseña un Quality Gate con estos valores:

* **Seguridad**: 0 Vulnerabilidades nuevas.
* **Tests**: 50% Coverage en código nuevo (en vez del 80% default).

**Esquema JSON (conceptual)**:

```json
{
  "conditions": [
    { "metric": "new_security_rating", "op": "LT", "error": "A" },
    { "metric": "new_coverage", "op": "GT", "error": "____" }
  ]
}
```

## Ejercicio: Clean as You Code

Tienes un proyecto con 500 bugs antiguos.
Hoy haces un PR que agrega una nueva funcionalidad impecable (0 bugs), pero el conteo total de bugs sigue siendo 500.

¿El Quality Gate predeterminado (SonarWay) debería pasar o fallar?

* [ ] Pasar (El código nuevo está limpio).
* [ ] Fallar (Aun hay 500 bugs en el sistema).

**Respuesta**: ______________________
