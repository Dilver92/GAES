﻿# GAES-HR V1.0.0 beta

GAES es un sistema de gestión de recursos humanos desarrollado con un enfoque en la simplicidad y eficiencia.

## Características principales

- Registro de empleados
- Gestión de usuarios (administrador)
- Edición de perfil de usuario
- Cambio de contraseña
- Actualización de foto de perfil
- Gestión de datos personales

## Tecnologías utilizadas

### Frontend
- Bootstrap v5.3
- HTML
- CSS
- JavaScript

### Backend
- PHP Version 8.2.12
- MariaDB 10.4.32
- Apache 2.4.58

## Requisitos del sistema

- PHP 8.2.12 o superior
- MariaDB 10.4.32 o superior
- Apache 2.4.58 o superior
- Extensiones PHP: mysqli, curl, mbstring

## Instalación en entorno local con XAMPP

1. Descargue e instale XAMPP desde [https://www.apachefriends.org/](https://www.apachefriends.org/)

2. Inicie XAMPP y asegúrese de que Apache y MySQL estén corriendo.

3. Clone el repositorio en la carpeta `htdocs` de XAMPP:
   \`\`\`
   cd C:\xampp\htdocs
   git clone https://github.com/joselib/GAES.git
   \`\`\`

4. Importe la base de datos:
   - Abra phpMyAdmin desde [http://localhost/phpmyadmin](http://localhost/phpmyadmin)
   - Cree una nueva base de datos llamada `gaes_db`
   - Seleccione la base de datos `gaes_db` y vaya a la pestaña "Importar"
   - Seleccione el archivo `db.sql` del proyecto y haga clic en "Importar"

5. Configure la conexión a la base de datos:
   - Copie el archivo `server-example.php` a `server.php`:
     \`\`\`
     cd C:\xampp\htdocs\GAES-HR
     copy server-example.php server.php
     \`\`\`
   - Abra `server.php` en un editor de texto y actualice las credenciales de la base de datos:
     \`\`\`php
     define('DB_HOST', 'localhost');
     define('DB_USER', 'root');
     define('DB_PASS', '');
     define('DB_NAME', 'gaes_db');
     \`\`\`

6. Configuración de Apache (opcional):
   - Si desea acceder al proyecto desde una URL personalizada, abra el archivo `C:\xampp\apache\conf\extra\httpd-vhosts.conf` y añada:
     \`\`\`
     <VirtualHost *:80>
         DocumentRoot "C:/xampp/htdocs/GAES"
         ServerName gaes.local
     </VirtualHost>
     \`\`\`
   - Luego, abra el archivo `C:\Windows\System32\drivers\etc\hosts` como administrador y añada:
     \`\`\`
     127.0.0.1 gaes.local
     \`\`\`

7. Reinicie Apache desde el panel de control de XAMPP.

8. Acceda a la aplicación:
   - Si configuró un virtual host: [http://gaes.local](http://gaes.local)
   - Si no configuró un virtual host: [http://localhost/GAES](http://localhost/GAES)

9. Credenciales de administrador por defecto:
   - Usuario: Administrador
   - Contraseña: Administrador

   **Importante**: Cambie estas credenciales inmediatamente después de su primer inicio de sesión.

## Solución de problemas

- Si encuentra errores relacionados con permisos, asegúrese de que el usuario del servidor web (generalmente `www-data` en sistemas Unix o el usuario con el que se ejecuta XAMPP en Windows) tenga permisos de lectura y escritura en el directorio del proyecto.
- Si las URL amigables no funcionan, asegúrese de que el módulo `mod_rewrite` de Apache esté habilitado en XAMPP.
- Para problemas de conexión a la base de datos, verifique que las credenciales en `server.php` sean correctas y que el servicio MySQL esté en ejecución.

Si encuentra algún otro problema durante la instalación, por favor, abra un issue en el repositorio de GitHub del proyecto.
