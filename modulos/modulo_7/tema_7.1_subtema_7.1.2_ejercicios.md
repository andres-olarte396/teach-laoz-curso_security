# Ejercicios: Creando la Wiki

## Ejercicio: Estructura de Wiki

Organiza las siguientes páginas en una jerarquía lógica de Wiki:

* Cómo rotar las claves de Azure.
* Lista de teléfonos de emergencia.
* Estándar de Nombres de Variables C#.
* Diagrama de Red de Producción.

**Propuesta**:

1. **Guías de Desarrollo**: (Estándar C#...)
2. **Infraestructura**: (Diagrama Red...)
3. **Operaciones / Runbooks**: (Rotar claves...)
4. **Respuesta a Incidentes**: (Teléfonos...)

## Ejercicio: Escribiendo un ADR

Completa este ADR sobre el uso de hashing:

**Título**: Uso de Argon2id para contraseñas.
**Contexto**: Actualmente usamos MD5, que es inseguro.
**Decisión**: Migrar todo a Argon2id.
**Consecuencias**:

* **Positivas**: Máxima seguridad contra ataques de fuerza bruta (GPU).
* **Negativas**: __________________________________________________ (Pista: Rendimiento/CPU).

**Respuesta**: El login será más lento (consumirá más CPU en el servidor) para calcular el hash.
