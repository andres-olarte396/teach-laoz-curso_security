# Ejercicios: OWASP Top 10

## Ejercicio 1. Identificación de Vulnerabilidades

Lee las siguientes descripciones y asigna la categoría OWASP Top 10 (A01-A10) correspondiente.

1. Un atacante modifica el ID en la URL de `/api/users/15` a `/api/users/16` y logra ver los datos de otro usuario sin ser administrador.
    * **Categoría**: ____________________ (Pista: A01)
2. La aplicación usa una librería de procesamiento de imágenes de 2018 que tiene 3 CVEs críticos reportados.
    * **Categoría**: ____________________ (Pista: A06)
3. Un formulario de búsqueda permite ingresar `' OR 1=1 --` y devuelve todos los registros de la tabla.
    * **Categoría**: ____________________ (Pista: A03)

## Ejercicio 2: Auditoría de Dependencias

Ejecuta el siguiente comando en una terminal de un proyecto .NET real o de prueba y analiza la salida.

```bash
dotnet list package --vulnerable
```

Si no tienes vulnerabilidades, ¡felicidades! Si las tienes, ¿cuál es el plan de acción sugerido?

1. Ignorarlas.
2. Actualizar el paquete a la versión parcheada.
3. Escribir tu propia versión de la librería.

**Respuesta**: ____________________
