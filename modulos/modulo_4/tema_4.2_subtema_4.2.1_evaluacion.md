# Evaluación: Integración CI/CD

### Pregunta 1

¿Por qué es necesario `fetch-depth: 0` (o git clone completo) para el análisis de SonarQube?

- a) Para descargar más rápido.
- [x] B) Porque SonarQube necesita el historial de Git para saber qué desarrollador escribió cada línea (Blame) y determinar qué es código nuevo.
- c) Para ocupar más espacio en disco.

### Pregunta 2

Para detener un despliegue si la calidad es baja, ¿qué paso adicional se necesita en el pipeline después del análisis?

- a) Enviar un email al jefe.
- [x] B) "Quality Gate Check" (o esperar el webhook de respuesta). Este paso consulta el estado del análisis y falla el build si es "Fail".
- c) Reiniciar el servidor.

### Pregunta 3

¿Es posible analizar proyectos .NET en un agente de build Linux?

- [x] A) Sí, .NET (Core / 5+) es multiplataforma y corre en Linux.
- b) No, solo en Windows.
