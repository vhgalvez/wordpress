# WordPress + JWT Authentication (Cream Magazine Theme)

Repositorio de configuración para un entorno WordPress con autenticación JWT (JSON Web Token), ideal para integraciones con APIs personalizadas, automatización de publicaciones, o apps externas.

---

## 🧩 Plugin Requerido

**JWT Authentication for WP REST API**

🔗 https://es.wordpress.org/plugins/jwt-authentication-for-wp-rest-api/  
🔗 GitHub: https://github.com/Tmeister/wp-api-jwt-auth

---

## ✅ Requisitos

- WordPress 5.x o 6.x
- PHP 7.4 o superior
- Acceso al archivo `wp-config.php`
- Acceso a plugins desde el panel de administración

---

## 🔐 Configuración paso a paso

### 1. Instalar y activar el plugin

Desde el panel de WordPress:
Plugins > Añadir nuevo > Buscar: JWT Authentication for WP REST API

less
Copiar
Editar
Haz clic en **Instalar** y luego en **Activar**.

---

### 2. Generar claves secretas (recomendado)

Usa el generador oficial para crear claves únicas de seguridad:

🔑 [https://api.wordpress.org/secret-key/1.1/salt/](https://api.wordpress.org/secret-key/1.1/salt/)

Copia las claves y pégalas dentro de `wp-config.php`, reemplazando las líneas predeterminadas:

```php
define('AUTH_KEY',         '...');
define('SECURE_AUTH_KEY',  '...');
define('LOGGED_IN_KEY',    '...');
define('NONCE_KEY',        '...');
define('AUTH_SALT',        '...');
define('SECURE_AUTH_SALT', '...');
define('LOGGED_IN_SALT',   '...');
define('NONCE_SALT',       '...');
3. Agregar clave secreta para JWT
En wp-config.php, agrega:

php
Copiar
Editar
define('JWT_AUTH_SECRET_KEY', 'TU_CLAVE_SECRETA_LARGA_GENERADA');
define('JWT_AUTH_CORS_ENABLE', true);
⚠️ La JWT_AUTH_SECRET_KEY no es un token, debe ser una cadena larga aleatoria generada por ti.

Puedes generar una clave segura con:

bash
Copiar
Editar
openssl rand -base64 64
4. (Opcional) Permitir HTTP en desarrollo
Solo si tu entorno no tiene HTTPS:

php
Copiar
Editar
define('JWT_AUTH_ALLOW_NONSECURE', true);
5. Obtener un token
Haz un POST a:

bash
Copiar
Editar
POST http://<tu-wordpress>/wp-json/jwt-auth/v1/token
Content-Type: application/json
Body:

json
Copiar
Editar
{
  "username": "usuario",
  "password": "contraseña"
}
Respuesta:

json
Copiar
Editar
{
  "token": "eyJ0eXAiOiJKV1QiLCJh...",
  "user_email": "user@example.com",
  "user_nicename": "usuario",
  "user_display_name": "Usuario"
}
6. Usar el token en peticiones protegidas
Agrega este encabezado a cualquier petición:

http
Copiar
Editar
Authorization: Bearer TU_TOKEN_AQUI
🎨 Tema activo
Este repositorio utiliza el tema:

Cream Magazine
🔗 https://wordpress.org/themes/cream-magazine/

🛠️ Archivos útiles
jwt_token.txt: contiene el último token generado.

generador_articulos.py: ejemplo de script que genera artículos usando OpenAI y los publica con JWT.

🧠 Créditos
Tmeister/wp-api-jwt-auth

OpenAI Python SDK

Tema: Cream Magazine

🔐 Seguridad
Mantén tu JWT_AUTH_SECRET_KEY fuera de versiones públicas del repositorio. Nunca compartas tus tokens JWT activos. Usa HTTPS en producción.

yaml
Copiar
Editar

---

openssl rand -base64 64
Ny6bLvblaI+SBwcQnf5ZJZGdxFN0Yq8VxOWortQDd1+LlYHQ2lT1tOLyxw38CYT064M6aOfPEJLK8Ri5I6d89A==