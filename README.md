# 🛡️ Curso: Seguridad Aplicada a .NET

> **“El código más seguro es aquel que se diseña con seguridad desde la primera línea.”**

---

## 🎯 Propósito del Curso

Este curso guía al estudiante en la aplicación práctica de **seguridad en entornos .NET**, abarcando desde los fundamentos hasta la integración de DevSecOps.  
Incluye el uso de estándares internacionales como **OWASP**, **Microsoft SDL**, **SonarQube** y **Fortinet**, para garantizar un desarrollo robusto, escalable y seguro.

---

## 🧩 1. Descripción General

| Campo                  | Detalle                                                      |
| ---------------------- | ------------------------------------------------------------ |
| **Versión**            | 1.0                                                          |
| **Estado**             | EN DESARROLLO                                                |
| **Duración total**     | 10 semanas                                                   |
| **Autor**              | Andrés Olarte                                                |
| **Modalidad**          | Teórico – Práctico (con laboratorios y ejercicios aplicados) |
| **Requisitos previos** | Conocimientos intermedios de .NET, Git y CI/CD.              |

---

## 🧭 2. Objetivos del Curso

1. Comprender los fundamentos de seguridad en desarrollo de software.
2. Aplicar el modelo **Microsoft SDL** al ciclo de vida de proyectos .NET.
3. Implementar controles de seguridad en código, configuración y autenticación.
4. Automatizar análisis estático y dinámico con **SonarQube** y **OWASP ZAP**.
5. Integrar soluciones de seguridad perimetral con **Fortinet**.
6. Realizar pruebas de vulnerabilidad y análisis de amenazas.
7. Documentar estándares de codificación segura y revisión técnica.
8. Implementar seguridad continua en pipelines **DevSecOps**.

---

## 🧱 3. Estructura del Curso

El curso está organizado en **módulos semanales**, cada uno con objetivos, prácticas y materiales de referencia.

| Semana | Módulo                               | Enfoque          | Resultado Esperado                                       |
| ------ | ------------------------------------ | ---------------- | -------------------------------------------------------- |
| 1      | Fundamentos de Seguridad             | Conceptual       | Comprensión del OWASP Top 10 y amenazas comunes          |
| 2      | Microsoft SDL                        | Teórico–Práctico | Aplicación de prácticas de seguridad en el ciclo de vida |
| 3      | Seguridad Aplicada a .NET            | Técnico          | Implementación de defensas en código y configuración     |
| 4      | Análisis Estático con SonarQube      | Hands-on         | Integración de análisis SAST en pipelines                |
| 5      | Fortinet y Seguridad en Red          | Técnico          | Configuración de políticas de red y filtrado perimetral  |
| 6      | Pruebas de Seguridad (Pentesting)    | Práctico         | Escaneo de APIs y generación de reportes ZAP             |
| 7      | Documentación y Base de Conocimiento | Conceptual       | Creación de manuales internos y checklist de revisión    |
| 8–10   | DevSecOps Avanzado                   | Integrador       | Seguridad continua con CI/CD y CodeQL                    |

---

## 📁 4. Estructura del Repositorio

```plaintext
📦 curso-seguridad-dotnet/
│
├── README.md                  # Descripción general del curso
├── curso.yaml                 # Archivo maestro de configuración
├── LICENSE                    # Licencia MIT
├── .gitignore                 # Archivos ignorados por Git
│
├── assets/                    # Recursos gráficos, diagramas o logos
├── docs/
│   ├── roadmap.md              # Ruta de aprendizaje y temario
│   ├── SECURITY_GUIDELINES.md  # Guía de codificación segura
│   └── CHECKLIST_QA.md         # Lista de control de calidad
│
├── phases/
│   ├── 01-fundamentos-seguridad/
│   ├── 02-microsoft-sdl/
│   ├── 03-seguridad-dotnet/
│   ├── 04-sonarqube/
│   ├── 05-fortinet/
│   ├── 06-pentesting/
│   ├── 07-documentacion/
│   └── 08-devsecops/
│
├── evaluations/               # Rúbricas, pruebas, y criterios de evaluación
└── community/                 # Contribuciones, foros, soporte y certificaciones
```

---

## 🧠 5. Metodología de Aprendizaje

Este curso aplica el modelo **70-20-10**:

- **70% práctica**: ejercicios, laboratorios y simulaciones reales.
- **20% colaboración**: revisiones de código y discusiones técnicas.
- **10% teoría**: fundamentos conceptuales, normas y frameworks.

Cada módulo incluye:

- 🔍 **Contexto teórico**
- 💻 **Laboratorio aplicado**
- 📋 **Checklist de seguridad**
- 🧾 **Evaluación corta**

---

## 📘 6. Recursos Clave

| Categoría           | Recurso                                                                   | Descripción                                       |
| ------------------- | ------------------------------------------------------------------------- | ------------------------------------------------- |
| **Normativas**      | [OWASP Top 10](https://owasp.org/Top10/)                                  | Estándar global de vulnerabilidades más comunes   |
| **Frameworks**      | [Microsoft SDL](https://learn.microsoft.com/en-us/security/sdl/practices) | Ciclo de desarrollo seguro                        |
| **Análisis**        | [SonarQube](https://www.sonarqube.org/)                                   | Análisis estático y gestión de calidad del código |
| **Infraestructura** | [Fortinet Knowledge Base](https://kb.fortinet.com/)                       | Seguridad perimetral y de red                     |
| **Testing**         | [OWASP ZAP](https://owasp.org/www-project-zap/)                           | Escaneo dinámico de vulnerabilidades              |
| **DevSecOps**       | [GitHub CodeQL](https://codeql.github.com/docs/codeql-for-csharp/)        | Escaneo semántico en CI/CD para .NET              |

---

## 🧮 7. Métricas de Calidad (QA Checklist)

| Categoría         | Métrica                                           | Estado |
| ----------------- | ------------------------------------------------- | ------ |
| 📂 Estructura     | Repositorio sigue la convención estándar          | [ ]    |
| 🧱 Modularización | Cada módulo tiene README, labs y evaluación       | [ ]    |
| 🧠 Contenido      | Explicaciones técnicas y ejemplos reales          | [ ]    |
| 💡 Prácticas      | Laboratorios funcionales verificados              | [ ]    |
| 🔐 Seguridad      | Sin datos sensibles ni secretos expuestos         | [ ]    |
| 🧰 Automatización | curso.yaml validado por `validate_yaml.py`        | [ ]    |
| 🎨 Diseño         | Markdown legible con emojis y headers jerárquicos | [ ]    |
| 📊 Evaluación     | Rúbricas claras y medibles                        | [ ]    |
| 🧾 Documentación  | Roadmap y manuales actualizados                   | [ ]    |
| 🧭 Navegación     | Enlaces previos y siguientes funcionales          | [ ]    |

---

## ⚙️ 8. Automatización y Scripts

| Script                        | Descripción                                    |
| ----------------------------- | ---------------------------------------------- |
| `scripts/generate_course.py`  | Genera carpetas y archivos según `curso.yaml`. |
| `scripts/validate_yaml.py`    | Valida la estructura y completitud del curso.  |
| `scripts/export_md_to_pdf.sh` | Exporta el curso completo a PDF para LMS.      |

### Ejemplo de uso

    ```bash
    python scripts/generate_course.py curso.yaml && python scripts/validate_yaml.py curso.yaml
    ```

---

## 🧩 9. Estándares de Redacción

- Mantén un tono profesional y técnico.
- Resalta conceptos clave en **negrita** y términos técnicos en _itálica_.
- Cada módulo debe contener valor nuevo, medible y aplicable.
- Usa emojis y separadores (`---`) para mejorar la lectura.
- Asegura que los ejemplos sean **reales y reproducibles** en .NET.

---

## 🏁 10. Publicación y Versionado

1. Completa los checklists de QA.
2. Ejecuta los scripts de validación.
3. Actualiza fecha de modificación en `curso.yaml`.
4. Realiza commit y push al repositorio:

   ```bash
   git add .
   git commit -m "🛡️ Curso Seguridad .NET - versión inicial"
   git push origin main
   ```

5. Usa **tags semánticos**: `v1.0`, `v1.1`, `v2.0`.

---

## 📊 11. Seguimiento del Progreso

| Semana | Módulo                   | Avance | Evidencia |
| ------ | ------------------------ | ------ | --------- |
| 1      | Fundamentos de Seguridad | ☐      |           |
| 2      | Microsoft SDL            | ☐      |           |
| 3      | Seguridad en .NET        | ☐      |           |
| 4      | SonarQube                | ☐      |           |
| 5      | Fortinet                 | ☐      |           |
| 6      | Pentesting               | ☐      |           |
| 7      | Documentación            | ☐      |           |
| 8–10   | DevSecOps Avanzado       | ☐      |           |

---

## 🧭 12. Conclusión

Este curso representa un camino integral hacia la **madurez en seguridad de software**, donde el desarrollador .NET evoluciona hacia un rol de **ingeniero seguro** con competencias en análisis, automatización y resiliencia.

> **“La seguridad no se agrega al final del desarrollo, se construye desde el diseño.”**

---

📅 **Última actualización:** `{{fecha_actual}}`
📜 **Licencia:** MIT
✍️ **Autor:** Andrés Olarte

---
