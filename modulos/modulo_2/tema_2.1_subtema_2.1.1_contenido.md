# Fases del Microsoft SDL

## 1. ¿Qué es el SDL?

El **Security Development Lifecycle (SDL)** de Microsoft es un proceso de aseguramiento de software que introduce la seguridad y la privacidad en todas las fases del desarrollo. No es una herramienta, es una metodología.

## 2. Las 7 Fases del SDL

### Fase 1. Entrenamiento (Training)

Antes de escribir una línea de código, el equipo debe conocer los conceptos básicos (como el OWASP Top 10).

* **Actividad**: Cursos de seguridad, concienciación.

### Fase 2: Requerimientos (Requirements)

Definir qué niveles de seguridad necesita la aplicación.

* **Actividad**: Definir "Quality Gates" de seguridad. ¿Qué pasa si descubrimos una vulnerabilidad crítica antes de salir a producción? (Respuesta SDL: No se sale).

### Fase 3: Diseño (Design)

Aquí se define la arquitectura segura.

* **Actividad**: Modelado de Amenazas (**Threat Modeling**) y Análisis de Superficie de Ataque.

### Fase 4: Implementación (Implementation)

Escribir código seguro.

* **Actividad**: Usar herramientas de análisis estático (SAST) en el IDE, prohibir funciones inseguras (`strcpy`, `MD5`).

### Fase 5: Verificación (Verification)

Comprobar que el código cumple con lo diseñado.

* **Actividad**: Análisis dinámico (DAST), Fuzzing, revisión manual de código.

### Fase 6: Lanzamiento (Release)

El plan de respuesta ante incidentes.

* **Actividad**: Final Security Review (FSR). ¿Estamos listos para resistir ataques reales?

### Fase 7: Respuesta (Response)

Qué hacer cuando (no si) ocurre un incidente.

* **Actividad**: Ejecutar el plan de respuesta y actualizar el proceso SDL con lo aprendido.

## 3. SDL en el Mundo Ágil

El SDL tradicional parece "Cascada", pero se adapta a Agile/DevOps:

* El **Threat Modeling** se hace por historia de usuario o épica.
* El **SAST** corre en cada Pull Request.
* La **Verificación** es continua en el pipeline CI/CD.
