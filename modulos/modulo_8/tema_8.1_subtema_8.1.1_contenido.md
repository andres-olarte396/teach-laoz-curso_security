# GitHub Advanced Security (GHAS)

## 1. CodeQL: El Motor

GitHub usa **CodeQL**, un motor semántico que trata el código como datos.
Puedes escribir consultas (`queries`) para encontrar patrones.

* "Encuentra todos los lugares donde un parámetro HTTP llega a una llamada `SqlCommand` sin sanitizar".

## 2. Dependabot

Mantiene tus dependencias al día automáticamente.

* **Security Updates**: Si `Newtonsoft.Json` tiene una vulnerabilidad crítica, Dependabot abre un PR automático actualizando a la versión segura. ¡Solo tienes que darle Merge!
* **Version Updates**: Mantiene todo fresco para evitar deuda técnica.

## 3. Secret Scanning

GitHub escanea cada push buscando patrones de claves (AWS, Azure, Stripe, etc.).

* Si encuentra una clave real, no solo te avisa, sino que (si tienes el "Push Protection" activado) **rechaza el push** para evitar que el secreto llegue al repositorio.

## 4. Branch Protection Rules

La regla de oro de DevSecOps:

* `Require status checks to pass before merging`.
* Añade "CodeQL" y "SonarCloud" como checks requeridos.
* Nadie, ni el jefe, puede saltarse esto.
