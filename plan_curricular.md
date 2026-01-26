# 🛡️ Roadmap de Aprendizaje en Seguridad Aplicada a .NET

> **Autor:** Andres Olarte  
> **Enfoque:** Seguridad del desarrollo en entornos .NET  
> **Duración estimada:** 10-12 semanas  
> **Propósito:** Integrar seguridad, estándares y automatización (DevSecOps) en proyectos .NET aplicando OWASP, Microsoft SDL, SonarQube y Fortinet.

---

## 📘 Objetivo General

Fortalecer las competencias en **seguridad del desarrollo de software**, integrando buenas prácticas, herramientas de análisis y cumplimiento en proyectos .NET, desde el diseño hasta la entrega continua.

---

## 🗂️ Estructura General del Roadmap

| Semana | Tema                              | Objetivo principal                                   |
| ------ | --------------------------------- | ---------------------------------------------------- |
| 1      | Fundamentos de seguridad          | Entender conceptos base y OWASP Top 10               |
| 2      | Microsoft SDL                     | Incorporar seguridad al ciclo de vida del software   |
| 3      | Seguridad aplicada a .NET         | Implementar protección en código y configuración     |
| 4      | SonarQube                         | Automatizar análisis estático y políticas de calidad |
| 5      | Fortinet y seguridad en red       | Integrar defensa perimetral e infraestructura        |
| 6      | Pruebas de seguridad (Pentesting) | Detectar vulnerabilidades y reforzar defensas        |
| 7      | Documentación y conocimiento      | Crear base de conocimiento y manuales internos       |
| 8-10   | DevSecOps avanzado                | Automatizar seguridad continua en pipelines          |

---

## 🥇 Semana 1 — Fundamentos de Seguridad en Desarrollo

### 🎯 Objetivos

- Comprender los principios de seguridad por diseño.
- Identificar las principales vulnerabilidades OWASP.
- Analizar amenazas y superficie de ataque.

### 🧩 Temas

- _Security by Design_ y _Defense in Depth_
- CIA Triad (Confidencialidad, Integridad, Disponibilidad)
- OWASP Top 10 (2021)
- Tipos de ataques (Injection, XSS, CSRF, DoS)

### 🧠 Recursos

- [OWASP Top 10](https://owasp.org/Top10/)
- [OWASP Cheat Sheet Series](https://cheatsheetseries.owasp.org/)
- [Microsoft Security Fundamentals](https://learn.microsoft.com/en-us/security/)

### 🧰 Tareas prácticas avanzadas

- [ ] Realiza un resumen de las 10 vulnerabilidades OWASP aplicadas a .NET.
- [ ] Analiza una aplicación .NET existente y lista posibles amenazas.
- [ ] Crea un documento `THREAT_MODEL.md` con el análisis.

---

## 🥈 Semana 2 — Seguridad en el Ciclo de Vida del Software (Microsoft SDL)

### 🎯 Objetivos

- Integrar seguridad en cada fase del ciclo de desarrollo.
- Aprender a crear modelos de amenazas.
- Aplicar revisiones de seguridad en PRs o pipelines.

### 🧩 Temas

- Fases del **Microsoft SDL**
- Threat Modeling Tool
- Secure Code Review Checklist
- Validación de dependencias (SBOM)

### 🧠 Recursos

- [Microsoft SDL Practices](https://learn.microsoft.com/en-us/security/sdl/practices)
- [Microsoft Threat Modeling Tool](https://learn.microsoft.com/en-us/security/engineering/threat-modeling-tool)
- [OWASP Secure Coding Practices](https://cheatsheetseries.owasp.org/)

### 🧰 Tareas prácticas

- [ ] Instala **Microsoft Threat Modeling Tool** y modela una API .NET.
- [ ] Genera un checklist interno de revisión de código seguro (`SECURE_CODE_REVIEW.md`).
- [ ] Agrega un paso de validación SDL en tu pipeline CI/CD.

---

## 🧱 Semana 3 — Seguridad Aplicada a .NET

### 🎯 Objetivos

- Implementar controles de seguridad en aplicaciones .NET.
- Configurar protección contra ataques comunes.
- Asegurar secretos y configuración.

### 🧩 Temas

- Autenticación (JWT, Identity, OAuth2, OpenID)
- Protección contra CSRF, XSS, SQL Injection
- Configuración segura (`appsettings.json`, `user-secrets`)
- Políticas de cabeceras (CSP, HSTS)
- Validación de entrada (`DataAnnotations`, `FluentValidation`)

### 🧠 Recursos

- [ASP.NET Core Security](https://learn.microsoft.com/en-us/aspnet/core/security/)
- [OWASP .NET Project](https://owasp.org/www-project-net/)
- [FluentValidation Docs](https://docs.fluentvalidation.net/en/latest/)

### 🧰 Tareas prácticas

- [ ] Implementa autenticación JWT en una API .NET.
- [ ] Aplica validación de entrada en controladores.
- [ ] Protege secretos con `dotnet user-secrets` o Azure Key Vault.
- [ ] Documenta las configuraciones seguras en `SECURITY_GUIDELINES.md`.

---

## 🧪 Semana 4 — Análisis Estático con SonarQube

### 🎯 Objetivos

- Automatizar la detección de vulnerabilidades en el código.
- Integrar SonarQube o SonarCloud con pipelines CI/CD.

### 🧩 Temas

- Instalación y configuración de **SonarQube**
- Reglas de seguridad y _Quality Gates_
- Integración con GitHub Actions / Azure DevOps
- Análisis de dependencias (OWASP Dependency Check)

### 🧠 Recursos

- [SonarQube for .NET](https://docs.sonarqube.org/latest/analysis/scan/sonarscanner-for-msbuild/)
- [SonarCloud GitHub Integration](https://sonarcloud.io/)
- [OWASP Dependency Check](https://owasp.org/www-project-dependency-check/)

### 🧰 Tareas prácticas

- [ ] Instala y configura SonarQube en local o cloud.
- [ ] Integra un escaneo de seguridad en tu pipeline.
- [ ] Configura una política _Quality Gate_ que bloquee despliegues inseguros.

---

## 🧰 Semana 5 — Seguridad en Red y Fortinet

### 🎯 Objetivos

- Comprender la seguridad perimetral y de red.
- Integrar Firewalls y WAFs en entornos corporativos o cloud.

### 🧩 Temas

- Segmentación de red y zonas seguras
- Políticas de acceso a APIs
- Firewalls FortiGate / FortiWeb
- Alertas y monitoreo (FortiAnalyzer, FortiSIEM)
- Logs .NET hacia SIEM

### 🧠 Recursos

- [Fortinet Training Institute](https://training.fortinet.com/)
- [Fortinet Knowledge Base](https://kb.fortinet.com/)
- [Microsoft Defender for Cloud Apps](https://learn.microsoft.com/en-us/defender-cloud-apps/)

### 🧰 Tareas prácticas

- [ ] Simula tráfico inseguro y analiza respuestas con WAF.
- [ ] Configura reglas FortiGate para filtrar endpoints.
- [ ] Integra logs de aplicación con FortiAnalyzer.

---

## ⚙️ Semana 6 — Pruebas de Seguridad y Pentesting Ético

### 🎯 Objetivos

- Detectar vulnerabilidades mediante herramientas de prueba.
- Analizar APIs y aplicaciones .NET en ejecución.

### 🧩 Temas

- Escaneo con OWASP ZAP y Burp Suite
- Fuzzing y pruebas automatizadas
- OWASP API Security Top 10
- Validación de dependencias NuGet

### 🧠 Recursos

- [OWASP ZAP](https://owasp.org/www-project-zap/)
- [Burp Suite](https://portswigger.net/burp/)
- [OWASP API Security Top 10](https://owasp.org/API-Security/)

### 🧰 Tareas prácticas

- [ ] Escanea tu API con OWASP ZAP.
- [ ] Genera un reporte de vulnerabilidades (`ZAP_REPORT.md`).
- [ ] Implementa correcciones y valida nuevamente.

---

## 📄 Semana 7 — Documentación y Base de Conocimiento

### 🎯 Objetivos

- Estandarizar las prácticas seguras.
- Crear una base de conocimiento viva y colaborativa.

### 🧩 Temas

- Manuales internos (`Secure Coding`, `Threat Modeling`)
- Checklist OWASP + SDL
- Repositorio central de conocimiento

### 🧠 Recursos

- [OWASP Cheat Sheet Series](https://cheatsheetseries.owasp.org/)
- [Microsoft Security Docs](https://learn.microsoft.com/en-us/security/)
- [SonarQube Rules for C#](https://rules.sonarsource.com/csharp)

### 🧰 Tareas prácticas

- [ ] Crea carpeta `/docs/security/` con guías y checklist.
- [ ] Documenta procedimientos de revisión (`SECURITY_REVIEW_GUIDE.md`).
- [ ] Publica ejemplos y buenas prácticas.

---

## 🚀 Semanas 8-10 — DevSecOps Avanzado

### 🎯 Objetivos

- Integrar seguridad continua en pipelines CI/CD.
- Automatizar escaneos SAST/DAST.
- Implementar monitoreo y alertas de seguridad.

### 🧩 Temas

- GitHub Advanced Security / CodeQL
- Integración de OWASP ZAP + SonarQube en CI/CD
- Azure DevOps Policies
- Monitoreo continuo (App Insights / SIEM)

### 🧠 Recursos

- [GitHub CodeQL for .NET](https://codeql.github.com/docs/codeql-for-csharp/)
- [OWASP DevSecOps Studio](https://owasp.org/www-project-devsecops-studio/)
- [Azure DevSecOps Practices](https://learn.microsoft.com/en-us/azure/devops/learn/security/)

### 🧰 Tareas prácticas

- [ ] Implementa un pipeline CI/CD que incluya:
  - Escaneo SonarQube (SAST)
  - Escaneo OWASP ZAP (DAST)
  - Validación de dependencias
  - Políticas de aprobación antes del despliegue
- [ ] Crea alertas automáticas ante vulnerabilidades críticas.

---

## 🧭 Resultado Esperado

Al finalizar este roadmap, habrás logrado:

- Diseñar y mantener sistemas .NET seguros.
- Detectar y mitigar vulnerabilidades OWASP.
- Automatizar revisiones de seguridad en pipelines CI/CD.
- Integrar Fortinet y SonarQube en ecosistemas DevSecOps.
- Construir una base sólida de seguridad aplicada al desarrollo profesional.

---

> 📘 **Consejo:** Versiona cada semana como una rama o carpeta (`/week-01`, `/week-02`, etc.) para mantener trazabilidad del avance.
