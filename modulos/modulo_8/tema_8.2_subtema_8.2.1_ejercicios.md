# Ejercicios: Monitoreo Ninja

## Ejercicio: KQL Básico

Tienes una tabla `requests` en App Insights.
Escribe una consulta (o pseudo-código) para encontrar las peticiones que devolvieron código 403 (Forbidden) en la última hora.

```kusto
requests
| where timestamp > ago(____)
| where resultCode == ____
| project timestamp, url, client_IP
```

**Respuesta**: 1h, 403.

## Ejercicio: Diseño de Respuesta

Detectas que un usuario está probando 1000 tarjetas de crédito por minuto (Brute Force).
Diseña el flujo de respuesta AUTOMÁTICO:

1. Application Insights detecta el pico de eventos.
2. Dispara un Webhook.
3. ¿Qué acción tomas automáticamente para detener el sangrado INMEDIATAMENTE?
    * [ ] Llamar al CEO.
    * [x] Bloquear/Suspender temporalmente la cuenta del usuario o banear su IP.
    * [ ] Apagar el servidor.

## Ejercicio: Post-Mortem

Después del incidente, ¿qué es lo más importante?

* [ ] Culpar a alguien.
* [ ] Escribir un reporte "Post-Mortem" sin culpa (Blameless), analizando la causa raíz y creando items de acción para que no se repita.

**Respuesta**: El reporte Blameless.
