# Azure Policy y Gobernanza Cloud

## 1. Gobernanza: Poniendo Orden en la Nube

En la nube, es fácil cometer errores.
"Oops, dejé el Storage Account público".
"Oops, creé una VM gigante y me costó $5000".
Azure Policy es el **guardarraíl** que evita que el coche se salga de la carretera.

## 2. Policy as Code

Las políticas de Azure definen reglas sobre tus recursos.
Se definen en JSON y se aplican a nivel de Suscripción o Grupo de Recursos.

### Ejemplos de Políticas Comunes

* **Allowed Locations**: "Solo se pueden crear recursos en `East US` y `West Europe`" (Soberanía de datos).
* **Secure Transfer Required**: "Todos los Storage Accounts deben requerir HTTPS".
* **SQL Encryption**: "Toda base de datos SQL debe tener TDE (Transparent Data Encryption) activado".

## 3. Efectos de la Política

* **Audit**: Te permite crear el recurso inseguro, pero lo marca en rojo en el dashboard de Compliance (útil para empezar).
* **Deny**: Bloquea la creación/actualización del recurso. El despliegue de Terraform/Bicep fallará.
* **DeployIfNotExists**: Si creas una VM y olvidas instalar el agente de monitoreo, Azure lo instala por ti automáticamente.

## 4. Microsoft Defender for Cloud

Es el "Posturómetro". Escanea tu suscripción y te da un **Secure Score** (ej. 65%).
Te da recomendaciones accionables: "Activa MFA para los admins", "Cierra el puerto RDP".
Gamifica la seguridad de la infraestructura.
