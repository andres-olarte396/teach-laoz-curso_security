# OWASP Top 10 (2021)

## 1. ¿Qué es OWASP?

El **Open Web Application Security Project (OWASP)** es una fundación sin fines de lucro que trabaja para mejorar la seguridad del software. Su documento más famoso es el **Top 10**, una lista de los riesgos de seguridad más críticos en aplicaciones web.

## 2. El Top 10 de 2021

La lista actual (la más reciente) incluye cambios significativos respecto a versiones anteriores.

1. **A01:2021 – Broken Access Control**: Fallos en las restricciones de lo que los usuarios autenticados pueden hacer.
2. **A02:2021 – Cryptographic Failures**: Antes conocido como "Sensitive Data Exposure". Datos no encriptados o criptografía débil.
3. **A03:2021 – Injection**: SQL Injection, Command Injection. Ahora incluye Cross-Site Scripting (XSS) como parte de esta categoría.
4. **A04:2021 – Insecure Design**: Nueva categoría centrada en riesgos relacionados con fallos de diseño y arquitectura.
5. **A05:2021 – Security Misconfiguration**: Configuraciones por defecto inseguras, mensajes de error detallados, buckets de nube abiertos.
6. **A06:2021 – Vulnerable and Outdated Components**: Uso de librerías con vulnerabilidades conocidas (CVEs).
7. **A07:2021 – Identification and Authentication Failures**: Fallos en login, gestión de sesiones, contraseñas débiles.
8. **A08:2021 – Software and Data Integrity Failures**: Fallos en actualizaciones de software, datos en pipelines CI/CD sin verificar.
9. **A09:2021 – Security Logging and Monitoring Failures**: No registrar eventos críticos o tardar en detectarlos.
10. **A10:2021 – Server-Side Request Forgery (SSRF)**: Permitir que el servidor haga peticiones a destinos no deseados.

## 3. Relevancia para .NET

Como desarrollador .NET, debes mapear estos riesgos a características del framework:

* **A01**: Usar correctamente `[Authorize]`, Policies y Claims.
* **A03**: Usar Entity Framework Core (evita SQL Injection básico) y encodeo de HTML (Razor lo hace por defecto).
* **A06**: Revisar dependencias NuGet con herramientas como `dotnet list package --vulnerable`.

> **Nota**: El Top 10 no es una lista exhaustiva, es un punto de partida para la concienciación.
