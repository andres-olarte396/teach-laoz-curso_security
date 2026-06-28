# Ejercicios: GHAS

## Ejercicio: Flujo de Dependabot

Recibes una notificación: "Dependabot alert: Critical severity vulnerability in Log4j".
Entras a GitHub.
Ves un Pull Request abierto por `app/dependabot` que sube la versión de 2.14 a 2.17.
El CI/CD corre en ese PR y pasa los tests (verde).

¿Qué haces?

1. Ignorarlo, tengo mucho trabajo.
2. Darle Merge inmediatamente.
3. Revisar el Changelog brevemente y darle Merge.

**Respuesta**: 3 (Siempre es bueno revisar, pero la prioridad es alta).

## Ejercicio: Secret Scanning

Intentas hacer `git push` y recibes:
`Remote: Error: Secret detection triggered. Found a possible Azure Storage Key in content.`

¿Qué haces?

* [ ] Usar `--force` o `--no-verify` para subirlo igual.
* [ ] Borrar la línea del archivo, revocar la clave en Azure (porque ya tocó tu disco local en texto plano), generar una nueva, guardarla en Key Vault/User Secrets, y volver a intentar.

**Respuesta**: La segunda opción. Si el scanner la vio, considera la clave quemada.
