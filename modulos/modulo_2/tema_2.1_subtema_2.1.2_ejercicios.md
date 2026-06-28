# Ejercicios: Modelado de Amenazas con STRIDE

## Ejercicio: Identificación de Amenazas

Imagina un sistema de Login de Cliebtes con Base de Datos.

1. El usuario envía su contraseña en texto plano por HTTP.
    * **Amenaza STRIDE**: __________________ (Pista: Information Disclosure)
2. Un usuario modifica la cookie de sesión para parecer el usuario 'admin'.
    * **Amenaza STRIDE**: __________________ (Pista: Spoofing o Elevation of Privilege)
3. Un atacante borra los logs del servidor para ocultar sus huellas.
    * **Amenaza STRIDE**: __________________ (Pista: Repudiation)

## Ejercicio: Diagrama mental

Identifica dónde pondrías un **Límite de Confianza (Trust Boundary)** en el siguiente flujo:

* Navegador del Usuario (Internet) -> Load Balancer -> API Web (Red Interna)

**Respuesta**:
El límite de confianza principal está entre __________________ y __________________.
