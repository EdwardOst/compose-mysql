# compose-mysql

Docker compose configuration for the Docker Hub mysql image.

### Environment Variables

Environment variables referenced in the `compose.yml` file are externalized in the `.env` file.
All environment variables follow the convention of defaulting to previously existing environment
variable values, a shell variable of the same name (lower case), or hardcoded default.  For example:

````bash
MYSQL_IMAGE=${MYSQL_IMAGE:-${mysql_image:-mysql}}
````
