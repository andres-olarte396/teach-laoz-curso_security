# Ejercicios: Logging Seguro

## Ejercicio: Datos Sensibles

Revisa este log y tacha (elimina) lo que nunca debería estar ahí:

`[INFO] Login exitoso. Usuario: jdoe, Password: SuperSecret123, IP: 192.168.1.5, TokenGenerado: eyJhbGci...`

**Versión Corregida**:
`[INFO] Login exitoso. Usuario: jdoe, IP: 192.168.1.5`

## Ejercicio: Correlación

Imagina que eres un SIEM. Recibes 2 eventos:

1. **FortiGate** (10:00 AM): Bloqueo de puerto 22 desde IP X.
2. **API .NET** (10:01 AM): Login exitoso del usuario 'admin' desde IP X.

¿Es esto sospechoso?

* [ ] No, son eventos independientes.
* [ ] Sí, parece que un atacante escaneó la red, encontró el puerto web abierto y luego comprometió una cuenta administrativa.

**Respuesta**: ______________________
