# Evaluación: SonarQube

### Pregunta 1

¿Por qué el comando `dotnet build` debe ejecutarse ENTRE el `begin` y el `end` del scanner?

- a) Porque es una regla arbitraria de Java.
- [x] B) Porque el análisis de .NET depende de Roslyn, que se ejecuta durante la compilación. El scanner se "engancha" al proceso de build.
- c) No es necesario, se puede hacer después.

### Pregunta 2

¿Qué es un **Security Hotspot** en SonarQube?

- a) Un lugar donde la oficina está muy caliente.
- b) Una vulnerabilidad confirmada.
- [x] C) Un fragmento de código sensible (ej. uso de criptografía) que la herramienta no puede determinar si es seguro o no, y requiere revisión humana.

### Pregunta 3

SAST significa:

- [x] A) Static Application Security Testing
- b) Server Administrator Security Tool
- c) Simple Audit System Test
