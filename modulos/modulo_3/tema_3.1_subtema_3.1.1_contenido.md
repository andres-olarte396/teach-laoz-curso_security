# Autenticación Moderna en .NET

## 1. El Paisaje de la Identidad

Olvídate de crear tu propia tabla de `Users` con contraseñas en Hash MD5. Eso es el pasado.
Hoy usamos estándares robustos: **OAuth 2.0** y **OpenID Connect (OIDC)**.

## 2. ASP.NET Core Identity

Es la solución "todo en uno" que viene con el framework.

* Maneja usuarios, contraseñas (con hashing fuerte PBKDF2), roles, Claims, tokens de email, 2FA.
* Se integra con Entity Framework Core (`IdentityDbContext`).

```csharp
// Program.cs
builder.Services.AddIdentity<IdentityUser, IdentityRole>()
    .AddEntityFrameworkStores<ApplicationDbContext>()
    .AddDefaultTokenProviders();
```

## 3. JWT (JSON Web Tokens)

Para APIs REST, no usamos cookies de sesión tradicionales. Usamos Tokens JWT.

* El cliente se loguea -> Recibe un Token.
* El cliente envía el Token en el header `Authorization: Bearer <token>` en cada petición.
* La API valida la firma del Token (sin ir a la base de datos).

```csharp
// Configuración de JWT Bearer
builder.Services.AddAuthentication(JwtBearerDefaults.AuthenticationScheme)
    .AddJwtBearer(options => {
        options.TokenValidationParameters = new TokenValidationParameters {
            ValidateIssuer = true,
            ValidateAudience = true,
            ValidateLifetime = true,
            ValidateIssuerSigningKey = true,
            ValidIssuer = builder.Configuration["Jwt:Issuer"],
            ValidAudience = builder.Configuration["Jwt:Audience"],
            IssuerSigningKey = new SymmetricSecurityKey(Encoding.UTF8.GetBytes(builder.Configuration["Jwt:Key"]))
        };
    });
```

## 4. Claims-Based Authorization

Ya no preguntamos `if (user.Role == "Admin")`. Preguntamos por **Claims** (afirmaciones).

* User tiene Claim `CanDeleteUsers = true`.
* User tiene Claim `Department = HR`.
* Esto permite políticas flexibles: `options.AddPolicy("HRManagers", policy => policy.RequireClaim("Department", "HR").RequireRole("Manager"));`
