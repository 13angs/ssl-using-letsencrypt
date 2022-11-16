# SSL using Letsencrypt

make sure to read the comment inside `docker-compose.yml` to further understand the example

## Start the services

- run the nginx-proxy and acme-companion service

```bash
docker compose up -d
```

## Secure the proxied containers

container listen on and expose port 80
1. make sure the service use the same network as nginx-proxy
2. change the `VIRTUAL_HOST` and `LETSENCRYPT_HOST` to your own domain

as for container listen on and expose another port than the default 80 you need to use `VIRTUAL_PORT` and set it your own port to force nginx-proxy to use the port


## Reference:
1. https://hub.docker.com/r/nginxproxy/acme-companion
2. https://hub.docker.com/r/jwilder/nginx-proxy
