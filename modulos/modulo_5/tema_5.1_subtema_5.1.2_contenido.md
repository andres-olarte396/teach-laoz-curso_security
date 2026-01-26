# El Ecosistema Fortinet

## 1. Más que un Firewall

Fortinet no solo vende "cajas". Ofrece el **Fortinet Security Fabric**, una plataforma integrada donde los dispositivos hablan entre sí.

## 2. Componentes Clave

### FortiGate (NGFW)

El corazón de la red.

* Firewall, VPN, Antivirus, IPS (Intrusion Prevention System).
* Puede desencriptar SSL para inspeccionar tráfico oculto.

### FortiWeb (WAF)

Específico para proteger aplicaciones web y APIs.

* Machine Learning para detectar anomalías (ej. un usuario haciendo scraping masivo).
* Protección avanzada contra OWASP Top 10.

### FortiSandbox

Un entorno aislado donde se detonan archivos sospechosos.

* Si un usuario sube un PDF a tu web, FortiWeb puede enviarlo al Sandbox antes de guardarlo.

## 3. Integración con DevSecOps

Fortinet se integra con pipelines CI/CD.

* **FortiDAST**: Puedes lanzar escaneos dinámicos contra tu aplicación en Staging automáticamente desde Jenkins o Azure DevOps.
* **Contenedores**: FortiWeb también existe como contenedor Docker/Kubernetes para proteger microservicios (WAF as a Service).
