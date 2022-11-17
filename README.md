# SSL using Letsencrypt

make sure to read the comment inside `docker-compose.yml` to further understand the example

## Run the nginx-proxy and acme-companion services

- jwilder/nginx-proxy sets up a container running nginx and docker-gen. docker-gen generates reverse proxy configs for nginx and reloads nginx when containers are started and stopped.
- The nginxproxy/acme-companion will handle the automated creation, renewal and use of SSL certificates for proxied Docker containers through the ACME protocol

to start first create a network used in the `docker-compose.yml` file

```bash
docker network create ssl-network
```

start the services

```bash
docker compose up -d
```

## Start securing the container

for container listen on and expose port 80

```bash
docker compose -f docker-compose.pma.yml up -d
```

for container listen on and expose another port than the default 80

```bash
docker compose -f docker-compose.pt.yml up -d
```

## Reference:
1. https://hub.docker.com/r/nginxproxy/acme-companion
2. https://hub.docker.com/r/jwilder/nginx-proxy
