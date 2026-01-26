# Evaluación: Gestión de Secretos

### Pregunta 1

¿Dónde se almacenan físicamente los "User Secrets" en Windows?

- a) En la carpeta `bin/Debug` del proyecto.
- [x] B) En el perfil del usuario (`%APPDATA%\Microsoft\UserSecrets`), fuera del repositorio de código.
- c) En la base de datos de registro de Windows.

### Pregunta 2

¿Cuál es la forma más segura de acceder a Azure Key Vault desde una App Service en Azure?

- a) Poniendo el ClientId y ClientSecret en el `appsettings.json`.
- [x] B) Usando "Managed Identity" (Identidad Administrada), que elimina la necesidad de gestionar credenciales manualmente.
- c) Dejando el Key Vault público.

### Pregunta 3

Si accidentalmente subes una API Key a un repositorio público de GitHub y la borras 5 minutos después:

- a) No pasa nada, nadie la vio.
- [x] B) Debes considerar la llave comprometida, revocarla y generar una nueva inmediatamente.
- c) Debes pedirle a GitHub que borre el historial.
