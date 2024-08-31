# Laravel 10 Auth Login System con verificación de email
Este proyecto implementa un sistema de autenticación utilizando Laravel 10, con verificación de email mediante Brevo (anteriormente Sendinblue). Incluye funcionalidades de registro de usuarios con confirmación de email, inicio de sesión y una página de información accesible solo para usuarios autenticados y verificados.
Características

## Página de inicio de sesión
- Página de registro de usuarios con verificación de email
- Envío de emails de confirmación usando Brevo
- Página de información protegida (solo accesible para usuarios autenticados y verificados)
- Desarrollado con Laravel 10

## Requisitos

- PHP 8.1 o superior
- Composer
- Node.js y npm
- MySQL
- Cuenta en Brevo (para el envío de emails)

## Instalación

1. Clonar el repositorio:
```sh
Copygit clone https://github.com/mariominondo/laravel-login-system.git
```

2. Navegar al directorio del proyecto:
```sh
cd laravel10-auth-email-verification
```

3. Instalar dependencias de PHP:
```sh
composer install
```

4. Instalar dependencias de JavaScript:
```sh
npm install
```

5. Copiar el archivo de configuración:
```sh
cp .env.example .env
```

6. Generar la clave de la aplicación:
```sh
php artisan key:generate
```

7. Configurar la base de datos en el archivo .env

8. Configurar Brevo en el archivo .env:
```sh
MAIL_MAILER=smtp
MAIL_HOST=smtp-relay.brevo.com
MAIL_PORT=587
MAIL_USERNAME=tu_usuario_brevo
MAIL_PASSWORD=tu_clave_brevo
MAIL_ENCRYPTION=tls
MAIL_FROM_ADDRESS="noreply@tudominio.com"
MAIL_FROM_NAME="${APP_NAME}"
```

9. Ejecutar las migraciones:
```sh
php artisan migrate
```

10. Compilar assets:
```sh
npm run dev
```

11. Iniciar el servidor de desarrollo:
```sh
php artisan serve
```

# Configuración de verificación de email

1. Asegúrate de que la opción QUEUE_CONNECTION en tu archivo .env esté configurada como database o redis para manejar los trabajos en cola de manera eficiente.

2. Ejecuta la migración para crear la tabla de trabajos:
```sh
php artisan queue:table
php artisan migrate
```

3. Inicia el worker de la cola:
```sh
php artisan queue:work
```

## Uso

1. Visita http://localhost:8000 en tu navegador para acceder a la aplicación.
2. Regístrate con tu email.
3. Recibirás un email de confirmación (verifica tu carpeta de spam si no lo ves).
4. Haz clic en el enlace de confirmación en el email.
5. Una vez verificado, podrás acceder a la página de información protegida.

## Contribuir

Las contribuciones son bienvenidas. Por favor, abre un issue para discutir los cambios importantes antes de crear un pull request.

## Licencia

MIT
