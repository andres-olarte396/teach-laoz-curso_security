# Defensa Perimetral y Seguridad en Red

## 1. El Castillo Digital

Antes de que un atacante toque tu API .NET, debe atravesar la red. Si la red es plana y abierta, tu aplicación es el único escudo. Si la red es segmentada y defendida, tienes múltiples oportunidades para detener el ataque.

## 2. Firewalls de Próxima Generación (NGFW)

Un firewall tradicional filtra por puerto e IP (Capa 3/4).
Un NGFW (como **FortiGate**) entiende aplicaciones (Capa 7).

* Sabe distinguir tráfico SQL de tráfico HTTP.
* Puede inspeccionar SSL (Desencriptar -> Analizar -> Encriptar).
* Tiene antivirus perimetral.

## 3. Web Application Firewall (WAF)

Es un firewall especializado en HTTP/HTTPS.

* Entiende qué es una SQL Injection o un XSS en la URL o el Body.
* **Virtual Patching**: Si tu aplicación tiene una vulnerabilidad y no puedes actualizarla hoy, el WAF puede bloquear el exploit específico antes de que llegue a tu servidor.

## 4. Segmentación de Red (Zero Trust)

No confíes en nadie, ni siquiera dentro de tu red.

* La API no debe ver Internet directamente.
* La Base de Datos no debe ver Internet NUNCA.
* La API solo debe poder hablar con la DB por el puerto 1433, nada más.

**En Azure**: Usar Virtual Networks (VNet), Network Security Groups (NSG) y Private Endpoints.
