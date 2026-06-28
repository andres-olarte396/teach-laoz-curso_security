# OWASP ZAP (Zed Attack Proxy)

## 1. DAST (Dynamic Application Security Testing)

A diferencia del SAST (SonarQube) que lee código estático, el **DAST** (OWASP ZAP) ataca la aplicación en ejecución.

* No necesita código fuente.
* Simula a un hacker real.

## 2. OWASP ZAP

Es la herramienta de seguridad DAST gratuita más popular del mundo.
Funciona como un **Proxy Man-in-the-Middle**.

* **Interceptación**: Te pones en medio del navegador y el servidor. Puedes ver y modificar cada petición HTTP al vuelo.
* **Spidering**: Rastrea tu sitio (crawling) para encontrar todas las URLs.
* **Active Scan**: Ataca cada URL encontrada con payloads conocidos (SQL Injections, XSS, etc.).

## 3. ZAP Heads-Up Display (HUD)

Una característica genial de ZAP es el HUD.
Inyecta una interfaz de control directamente en tu navegador (Firefox/Chrome).

* Puedes ver alertas de seguridad en tiempo real mientras navegas tu propia app.
* Puedes "romper" (Break) una petición al pulsar un botón y modificarla antes de enviarla.

## 4. Automatización

ZAP tiene una API robusta y un modo Docker (`owasp/zap2docker-stable`).
Esto permite correr "Baseline Scans" en tu pipeline de CI/CD.
