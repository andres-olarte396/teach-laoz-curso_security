# Ejercicios: Pipelines Seguros

## Ejercicio: Diagrama de Pipeline

Dibuja (o describe) el flujo ideal de un pipeline de CI con análisis de seguridad.
Arrastra los siguientes pasos al orden correcto:

* [ ] Deploy to Staging
* [ ] Checkout Code
* [ ] SonarQube Begin
* [ ] SonarQube End
* [ ] Dotnet Build
* [ ] Unit Tests

**Orden Correcto**:
1 -> Checkout Code
2 -> __________________
3 -> __________________
4 -> __________________
5 -> __________________
6 -> Deploy to Staging

## Ejercicio: Depuración de Errores

Tu pipeline falla con el error:
`"The only way to get an accurate analysis of C# projects is to run the analysis during the build."`

¿Qué pasó?

1. Olvidaste instalar Java.
2. Ejecutaste el paso `SonarQube End` antes del `Build`.
3. Ejecutaste el `Build` fuera del bloque `Begin` / `End`.

**Respuesta**: ______________________
