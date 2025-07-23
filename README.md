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
# Vault (official)
- Directly runned from docker hub in docker desktop
- keys were displayed in the logs of the container

# Click House (official)
- Directly runned from docker hub in docker desktop
- default username & password is admin

# ActiveMQ (rmohr/activemq:latest)
- Directly runned from docker hub in docker desktop

# Cassandra (official)
- Directly runned from docker hub in docker desktop

# Elasticsearch (official)
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
# Opensearch
- using docker compose
```
version: '3'
services:
  opensearch:
    image: opensearchproject/opensearch:2.14.0
    container_name: opensearch
    environment:
      - discovery.type=single-node
      - plugins.security.disabled=true
      - OPENSEARCH_JAVA_OPTS=-Xms512m -Xmx512m
      - OPENSEARCH_INITIAL_ADMIN_PASSWORD=Shyam@184239!
    ports:
      - "9200:9200"
    volumes:
      - opensearch-data:/usr/share/opensearch/data

  dashboards:
    image: opensearchproject/opensearch-dashboards:2.14.0
    container_name: dashboards
    ports:
      - "5601:5601"
    environment:
      - OPENSEARCH_HOSTS=["http://opensearch:9200"]
      - DISABLE_SECURITY_DASHBOARDS_PLUGIN=true

volumes:
  opensearch-data:
```
