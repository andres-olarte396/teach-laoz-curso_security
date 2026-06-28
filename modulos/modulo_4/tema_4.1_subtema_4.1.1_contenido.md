# Configuración de SonarQube para .NET

## 1. ¿Qué es SonarQube?

Es la herramienta estándar de la industria para **SAST (Static Application Security Testing)**.
Analiza tu código fuente sin ejecutarlo y busca:

* **Bugs**: Errores lógicos.
* **Vulnerabilidades**: Fallos de seguridad (SQL Injection, XSS).
* **Code Smells**: Código mantenible pero "feo" o difícil de entender.
* **Hotspots**: Áreas críticas que requieren revisión manual.

## 2. Instalación con Docker

La forma más rápida de tener un servidor SonarQube local.

```bash
docker run -d --name sonarqube -p 9000:9000 -e SONAR_ES_BOOTSTRAP_CHECKS_DISABLE=true sonarqube:lts
# Acceder a http://localhost:9000 (admin/admin)
```

## 3. El Scanner para .NET

Para analizar un proyecto .NET, necesitas el **SonarScanner for .NET**.
Es una herramienta global de CLI.

```bash
dotnet tool install --global dotnet-sonarscanner
```

## 4. Ejecutando el Análisis

El análisis ocurre *durante* la compilación (Build).
Son 3 pasos obligatorios:

1. **Begin**: Prepara el análisis y conecta con el servidor.

    ```bash
    dotnet sonarscanner begin /k:"mi-proyecto" /d:sonar.login="token"
    ```

2. **Build**: Compila el código (MsBuild hace el trabajo pesado del análisis aquí).

    ```bash
    dotnet build
    ```

3. **End**: Envía los resultados al servidor para su procesamiento.

    ```bash
    dotnet sonarscanner end /d:sonar.login="token"
    ```
