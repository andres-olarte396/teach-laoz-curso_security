# Ejercicios: Atacando con ZAP

## Ejercicio: Concepto de Proxy

Si configuras tu navegador para usar ZAP como proxy (localhost:8080), y entras a `https://google.com`, ¿qué certificado SSL verás en el navegador?

1. El certificado real de Google firmado por Google Trust Services.
2. Un certificado autofirmado generado por OWASP ZAP Root CA.

**Respuesta**: ____________________ (Pista: Para interceptar HTTPS, el proxy debe desencriptar y re-encriptar, por lo que el navegador ve el certificado del proxy).

## Ejercicio: Active Scan

Lanzas un Active Scan contra tu sitio de desarrollo. ZAP reporta "SQL Injection" en `/api/search?q=...`.
El payload que usó ZAP fue `' OR '1'='1`.
¿Qué significa esto?

* [ ] Que ZAP hackeó la base de datos y borró todo.
* [ ] Que ZAP envió ese texto y detectó una anomalía en la respuesta (ej. tardó más tiempo, o devolvió datos de más), indicando una posible vulnerabilidad.

**Respuesta**: ______________________
