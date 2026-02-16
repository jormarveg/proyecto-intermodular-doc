---
layout: default
title: Instalación
nav_order: 3
---

# Instalación

Se detallan los pasos necesarios para desplegar **LogNow!** en un entorno local de desarrollo (Stack LEMP).

## Requisitos

- **Servidor Web:** Nginx.
- **Intérprete:** PHP 8.0 o superior (con extensión `php-fpm`).
- **Base de Datos:** MySQL 8.0.
- **Control de versiones:** Git.

## Pasos de instalación

### 1. Despliegue

Clona el repositorio en el directorio raíz configurado en tu servidor web (habitualmente `/var/www/html/` en entornos Linux).

```bash
cd /var/www/html
git clone https://github.com/usuario/LogNow.git
```

---

### 2. Configuración

Configura en Nginx el bloque del servidor para procesar archivos PHP. Asegúrate de que tu configuración (habitualmente en `/etc/nginx/sites-available/default`) incluye las directivas para `fastcgi`:

```nginx
server {
    listen 80;
    server_name localhost;
    root /var/www/html/LogNow;
    index index.php index.html;

    location / {
        try_files $uri $uri/ =404;
    }

    location ~ \.php$ {
        include snippets/fastcgi-php.conf;
        fastcgi_pass unix:/run/php/php8.0-fpm.sock;
    }
}
```

Reinicia Nginx tras los cambios: `sudo systemctl restart nginx`.

### 3. Inicialización de la base de datos

1.  Accede a MySQL y crea la base de datos:
    ```sql
    CREATE DATABASE LogNow;
    ```
2.  Ejecuta el [Script SQL](arquitectura.md) de inicialización.

### 4. Configuración de entorno


Crea un archivo `config.php` en la raíz del proyecto.

```php
<?php
define('DB_HOST', 'localhost');
define('DB_NAME', 'LogNow');
define('DB_USER', 'usuario');
define('DB_PASS', 'contraseña');
?>
```

## Comprobación

Accede a `http://localhost/` en el navegador. Deberías ver la pantalla de bienvenida.
