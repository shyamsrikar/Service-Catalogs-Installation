# Service-Catalogs-Installation
# PostgreSQL
```
docker run -d \
  --name my-postgres \
  -e POSTGRES_USER=myuser \
  -e POSTGRES_PASSWORD=mypassword \
  -e POSTGRES_DB=mydatabase \
  -p 5432:5432 \
  postgres:latest
```
# RabbitMQ
```
docker run -d \
  --hostname my-rabbit \
  --name some-rabbit \
  -e RABBITMQ_DEFAULT_USER=user \
  -e RABBITMQ_DEFAULT_PASS=password \
  -p 5672:5672 \
  -p 15672:15672 \
  rabbitmq:3-management
```
# Vault
```
- Directly runned from docker hub in docker desktop
- keys were displayed in the logs of the container
```
# Click House
- Directly runned from docker hub in docker desktop
- default username & password is admin

# ActiveMQ
- Directly runned from docker hub in docker desktop

# Cassandra
- Directly runned from docker hub in docker desktop

# MariaDB
```
docker run --detach --name some-mariadb \
  -p 3306:3306 \
  --env MARIADB_USER=example-user \
  --env MARIADB_PASSWORD=password \
  --env MARIADB_DATABASE=database \
  --env MARIADB_ROOT_PASSWORD=rootpassword \
  mariadb:latest
```
