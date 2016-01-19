FROM mysql:latest

# Copy the database initialize script:
# Contents of /docker-entrypoint-initdb.d are run on mysqld startup
ADD ./ /docker-entrypoint-initdb.d/

# Default values for passwords and database name. Can be overridden on docker run
ENV MYSQL_DATABASE=wordpress
ENV MYSQL_ROOT_USER=root
ENV MYSQL_ROOT_PASSWORD=root