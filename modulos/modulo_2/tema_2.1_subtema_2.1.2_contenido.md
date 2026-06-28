# Modelado de Amenazas (Threat Modeling)

## 1. ¿Qué es el Modelado de Amenazas?

Es un proceso estructurado para idenficar posibles riesgos de seguridad (amenazas) en tu aplicación y determinar cómo mitigarlos.
No se trata de revisar código, sino de revisar la **arquitectura** y el **flujo de datos**.

## 2. Microsoft Threat Modeling Tool

Microsoft ofrece una herramienta gratuita que permite dibujar diagramas de flujo de datos (DFD) y genera automáticamente una lista de amenazas potenciales basadas en el marco **STRIDE**.

### Elementos de un DFD

* **Procesos**: Tu aplicación web, servicio de Windows.
* **Almacenes de Datos**: Base de datos, sistema de archivos, registro.
* **Flujo de Datos**: Movimiento de información entre procesos y almacenes.
* **Entidades Externas**: Usuarios, sistemas de terceros.
* **Límites de Confianza (Trust Boundaries)**: La línea que separa lo "confiable" (tu intranet) de lo "no confiable" (Internet). **Aquí es donde ocurren los ataques.**

## 3. Metodología STRIDE

Es un acrónimo para clasificar amenazas:

1. **S - Spoofing (Suplantación)**: Hacerse pasar por otro.
    * *Mitigación*: Autenticación fuerte.
2. **T - Tampering (Manipulación)**: Modificar datos en tránsito o reposo.
    * *Mitigación*: Integridad (Firmas, Hashing).
3. **R - Repudiation (Repudio)**: Negar haber realizado una acción.
    * *Mitigación*: Logs de auditoría no repudiables.
4. **I - Information Disclosure (Divulgación)**: Exponer datos privados.
    * *Mitigación*: Encriptación.
5. **D - Denial of Service (Denegación)**: Tumbar el servicio.
    * *Mitigación*: Resiliencia, filtrado.
6. **E - Elevation of Privilege (Elevación)**: Ganar permisos de admin.
    * *Mitigación*: Autorización robusta.

## 4. Práctica

El Threat Modeling debe hacerse **antes** de codificar una nueva funcionalidad crítica.

1. Dibujar el sistema.
2. Analizar STRIDE por cada elemento.
3. Definir mitigaciones.
4. Validar mitigaciones.
