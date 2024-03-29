## MariaDB Docker Compose 

Archivo de docker compose para crear una pila con MariaDB y PHPmyAdmin
Variables de entorno en archivo externo

![MariaDB](mariadb.png)


**Requisitos:**

- Máquina con Docker y Docker Compose.

- Instalar MariaDB client

- Crear carpeta Compose/MariaDB

Crear archivo docker-compose.yaml adjunto

Lanzar el stack:

    docker compose up -d

Si todo termina correctamente podemos administrar la base de datos de 2 formas:

- Desde phpmyadmin desde un navegador a traves de la URL:

    http://localhost:8080

- Desde un terminal con el comando:

(Como administrador)
    
    mariadb -u root -h 127.0.0.1 -p 

(Como usuario estandar)

    mariadb -u user -h 127.0.0.1 -p  
    
Si recibimos el error:

*Can't connect to local MariaDB server through socket '/var/run/mysqld/mysqld.sock' (2)' -- Missing /var/run/mysqld/mysqld.sock*

podemos usar el comando:

    mariadb --protocol=tcp -u root -p
    
Podemos crear un alias en linux para evitar usar todo el comando anterior, creando un alias para cada usuario:

    alias mariadbr="mariadb  --protocol=tcp -u root -p"
y
     
    alias mariadbu="mariadb  --protocol=tcp -u user -p"
    

Tambien podemos utilizar software de terceros como DBeaver. DBeaver es una herramienta de base de datos universal gratuita y de código abierto para desarrolladores y administradores de bases de datos.

Puedes descargar [DBeaver desde su web oficial ](https://dbeaver.io/).


![Captura de pantalla](images/mock_data.png)

