# compose-mysql

Docker Compose using the Docker Hub [Mysql](https://hub.docker.com/_/mysql) image.

### Running Server

To run the mysql server

    docker compose up -d

To run the mysql client in attached mode

    docker compose run --rm mysql_client

To run [adminer](https://hub.docker.com/_/adminer)

    docker compose --profile admin up -d

Adminer (formerly phpMinAdmn) will run on a dynamically assigned port.
You can get the dymamic port from the docker desktop gui, or use docker inspect:

    docker inspect --format '{{ (index .NetworkSettings.Ports "8080/tcp" 0).HostPort }}' <adminer_container_name>

### Granting Remote Access Rights

Grant permissions to a user `user` to login from any remote machine to the a database `db`.

 GRANT ALL PRIVILEGES ON db to 'user'@'%';
 
