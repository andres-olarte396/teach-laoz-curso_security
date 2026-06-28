# Integración en Pipelines CI/CD

## 1. Automatización es la Clave

Ejecutar el scanner manualmente en tu laptop está bien para probar, pero la verdadera seguridad viene de la automatización. Cada Commit y cada Pull Request deben ser analizados.

## 2. GitHub Actions

Integrar SonarCloud (la versión SaaS) o un SonarQube expuesto es muy fácil con Actions.

```yaml
name: Build
on:
  push:
    branches:
      - main
  pull_request:
    types: [opened, synchronize, reopened]
jobs:
  build:
    runs-on: windows-latest
    steps:
      - uses: actions/checkout@v2
        with:
          fetch-depth: 0  # Importante para detección de 'New Code'
      - name: Set up JDK 11
        uses: actions/setup-java@v1
        with:
          java-version: 1.11
      - name: Cache SonarCloud packages
        uses: actions/cache@v1
        # ... configuración de caché ...
      - name: Build and analyze
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}  # Necesario para comentar en PRs
          SONAR_TOKEN: ${{ secrets.SONAR_TOKEN }}
        shell: powershell
        run: |
          .\.sonar\scanner\dotnet-sonarscanner begin /k:"key" /o:"org" /d:sonar.login="${{ secrets.SONAR_TOKEN }}" /d:sonar.host.url="https://sonarcloud.io"
          dotnet build
          .\.sonar\scanner\dotnet-sonarscanner end /d:sonar.login="${{ secrets.SONAR_TOKEN }}"
```

## 3. Azure DevOps

En Azure Pipelines, hay tareas nativas en el Marketplace ("SonarQube Prepare", "Run Code Analysis", "Publish Quality Gate Result").
La lógica es idéntica: Prepare -> Build -> Analyze -> Publish.

## 4. Bloqueo de Pull Requests

La "Killer Feature":
Si configuras la **Branch Policy** para requerir que el "Status Check" de SonarQube esté en verde, es físicamente imposible mergear código inseguro a la rama `main`.
Esto es DevSecOps real.
