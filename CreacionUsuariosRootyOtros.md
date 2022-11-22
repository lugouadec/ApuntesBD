# Crear Usuarios Root en MySql 8 y MariaDB 10.X

Crear un usuario y establecer una contraseña establecer una contraseña con los maximos privilegios es muy sencillo hacerlo desde comandos.

Primero debes conectarte con el motor de BBDD, con el usuario root o con privilegios para crear otros usuario y privilegios:

    mysql -u root -p

    (pedirá la clave).

Una vez dentro a mi me gusta ver las bases de datos:

    show databases;

Para crear el usuario:

    CREATE USER 'usuario'@'localhost' IDENTIFIED VIA mysql_native_password;

Ahora le establecemos una password:

    SET PASSWORD FOR 'usuario'@'localhost' = PASSWORD('patata');

Le damos todos los privilegios sobre esta base de datos al usuario recién creado:

    GRANT ALL PRIVILEGES ON *.* TO 'usuario'@'localhost';

## Codigo de Ejemplo

    CREATE USER 'usuario'@'localhost' IDENTIFIED VIA mysql_native_password;
    SET PASSWORD FOR 'usuario'@'localhost' = PASSWORD('patata');
    GRANT ALL PRIVILEGES ON *.* TO 'usuario'@'localhost';

## Crea Usuarios con todos los permisos sobre una Base de Datos con el mismo Nombre

Crear usuario, establecer una contraseña y crear una base de datos en MariaDB o MySQL es muy sencillo, y no necesitáis el uso de ningún “panel“.

Es muy sencillo hacerlo desde comandos y no requiere que instales paneles “vulnerables” como phpMyAdmin.

Lo primero conectar con el motor de BBDD, con un usuario con privilegios para crear otros usuario y bases de datos, suele ser el usuario root:

    mysql -u root -p

    (pedirá la clave).

Una vez dentro a mi me gusta ver las bases de datos:

    show databases;

Para crear el usuario:

    CREATE USER 'usuario'@'localhost' IDENTIFIED VIA mysql_native_password;

Ahora le establecemos una password:

    SET PASSWORD FOR 'usuario'@'localhost' = PASSWORD('patata');

Creamos la base de datos:

    CREATE DATABASE IF NOT EXISTS `usuario`;

Le damos todos los privilegios sobre esta base de datos al usuario recién creado:

    GRANT ALL PRIVILEGES ON `usuario`.* TO 'usuario'@'localhost';

## Codigo de Ejemplo

    CREATE USER 'usuario'@'localhost' IDENTIFIED VIA mysql_native_password;
    SET PASSWORD FOR 'usuario'@'localhost' = PASSWORD('patata');
    CREATE DATABASE IF NOT EXISTS `usuario`;
    GRANT ALL PRIVILEGES ON `usuario`.* TO 'usuario'@'localhost';