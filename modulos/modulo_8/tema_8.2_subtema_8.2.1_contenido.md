# Monitoreo Proactivo y Respuesta (Application Insights)

## 1. Detectar antes que el Cliente

La meta es simple: Saber que algo va mal antes de que el usuario ponga un tweet enojado.
**Application Insights** es el APM (Application Performance Monitor) de Azure.

## 2. Detección de Anomalías

App Insights usa Machine Learning para aprender el patrón normal de tu app.

* "Normalmente falla el 1% de los logins".
* "Hoy está fallando el 15%". -> **ALERTA INTELIGENTE**.
* No tuviste que configurar un umbral manual. La IA lo detectó.

## 3. Logs de Seguridad en App Insights

Puedes enviar eventos de seguridad específicos (AppEvents) y luego consultarlos con KQL (Kusto Query Language).

```csharp
telemetryClient.TrackEvent("SecurityRisk", new Dictionary<string, string> {
    { "Type", "IDOR_Attempt" },
    { "TargetResource", "Invoice_123" },
    { "User", "Attacker" }
});
```

Query KQL:

```kusto
customEvents
| where name == "SecurityRisk"
| summarize count() by User
| where count_ > 10
```

## 4. Respuesta Automatizada (Logic Apps)

¿Qué pasa cuando KQL detecta esa alerta?
Puede disparar una **Azure Logic App** (flujo visual).

* Paso 1. Recibir Alerta.
* Paso 2: Bloquear la IP en el Azure Firewall.
* Paso 3: Enviar mensaje a Slack/Teams del equipo de seguridad.
* Paso 4: Crear ticket en Jira.

Esto es SOAR (Security Orchestration, Automation, and Response) simplificado.
