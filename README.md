# Security Portfolio

### Handlungsziel 1: recognizing threats
##### Bösartige Bedrohungen können in eine oder mehrere der folgenden Kategorien eingeteilt werden:

![OWASP_Top10](https://github.com/Rosidvas/LB-M183-Studer/assets/89085444/0cdd4781-6c31-4f5c-8817-1b2d23a4530e)


```
services.AddAuthentication(options =>
{
    options.DefaultAuthenticateScheme = JwtBearerDefaults.AuthenticationScheme;
    options.DefaultChallengeScheme = JwtBearerDefaults.AuthenticationScheme;
}).AddJwtBearer(options =>
{
    options.TokenValidationParameters = new TokenValidationParameters
    {
        ValidateIssuer = true,
        ValidateAudience = true,
        ValidateLifetime = true,
        ValidateIssuerSigningKey = true,
        ValidIssuer = Configuration["Jwt:Issuer"],
        ValidAudience = Configuration["Jwt:Audience"],
        IssuerSigningKey = new SymmetricSecurityKey(Encoding.UTF8.GetBytes(Configuration["Jwt:Key"]))
    };
});
```
