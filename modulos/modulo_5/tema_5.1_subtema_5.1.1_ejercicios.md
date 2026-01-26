# Ejercicios: Arquitectura de Red

## Ejercicio: Diseño Seguro

Tienes 3 componentes:

1. Frontend React (Público).
2. Backend API .NET.
3. SQL Server.

Dibuja las reglas de firewall (NSG) necesarias:

* **Frontend**: Permite entrada HTTP/S desde `0.0.0.0/0` (Internet).
* **Backend**:
  * Entrada desde: __________________ (Solo el Frontend).
  * Salida hacia: __________________ (Solo la DB y quizás APIs externas).
* **SQL Server**:
  * Entrada desde: __________________ (Solo el Backend).
  * Salida hacia: Bloqueado (Internet).

## Ejercicio: WAF

¿Cuál de estos ataques bloquearía mejor un WAF que un Firewall tradicional?

* [ ] Un escaneo de puertos (Nmap).
* [ ] Un intento de SQL Injection en un formulario de búsqueda (`' OR 1=1`).
* [ ] Un ataque volumétrico (DDoS) a nivel de red (UDP Flood).

**Respuesta**: ______________________
