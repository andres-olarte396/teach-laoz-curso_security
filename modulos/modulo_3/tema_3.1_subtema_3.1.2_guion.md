# Guion de Audio - 3.1.2 Defensas Web

**Locutor**: "Ya conocemos los ataques, ahora levantemos los escudos."

**Locutor**: "En .NET, muchas defensas vienen 'de fábrica'. Razor bloquea XSS, y Entity Framework bloquea SQL Injection... siempre y cuando no los obligues a ser inseguros. El problema suele ser el error humano: usar `Html.Raw` innecesariamente o concatenar SQL a mano."

**Locutor**: "Un detalle importante: Las redirecciones. Si tu login redirige a donde diga la URL, un atacante puede crear un link de login real que redirige a su sitio falso. Siempre usa `LocalRedirect` o valida que la URL destino sea de tu propiedad."
