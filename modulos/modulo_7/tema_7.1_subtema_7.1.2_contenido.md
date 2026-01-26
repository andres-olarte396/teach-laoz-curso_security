# Base de Conocimiento y Wiki

## 1. El Wiki de Seguridad

Cada equipo de desarrollo debería mantener un Wiki (en Azure DevOps, GitHub Wiki o Confluence).
¿Qué debe tener?

### Inventario de Activos

* Lista de dominios, IPs y certificados SSL (y cuándo vencen).
* Lista de librerías de terceros aprobadas.

### Respuestas a Incidentes

* "¿A quién llamo si la base de datos se borró a las 3 AM?"
* Diagrama de flujo de escalamiento.

### Modelos de Amenazas

* Los diagramas y documentos que generamos en el Módulo 2 deben vivir aquí y actualizarse.

## 2. ADRs (Architecture Decision Records)

Cuando tomes una decisión importante de seguridad (ej. "Usaremos Auth0 en lugar de IdentityServer"), documenta el **POR QUÉ**.

* **Contexto**: Necesitamos SSO.
* **Decisión**: Usar Auth0.
* **Consecuencias**: Costo mensual, pero menos mantenimiento.

Esto evita que, dentro de un año, alguien diga: "¿Por qué estamos pagando esto?" y lo quite sin entender el riesgo.
