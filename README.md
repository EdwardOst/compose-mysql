# compose-mysql

Docker Compose using the Docker Hub [Mysql](https://hub.docker.com/_/mysql) image.

### Environment Variables

Environment variables referenced in the `compose.yml` file are externalized in the `.env` file.
All environment variables follow the convention of defaulting to previously existing environment
variable values, a shell variable of the same name (lower case), or hardcoded default.  For example:

````bash
MYSQL_IMAGE=${MYSQL_IMAGE:-${mysql_image:-mysql}}
````

### Running Server

To run the mysql server

    docker compose up -d

To run the mysql client

    docker compose --profile client run mysql_client

The mysql client runs in commandline mode so it needs to be attached.

### Granting Remote Access Rights

Grant permissions to the default user `admin` to login from a remote machine to the default database `qlik`.

 GRANT ALL PRIVILEGES ON qlik to 'admin'@'%';
 
