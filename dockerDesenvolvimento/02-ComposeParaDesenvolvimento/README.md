# comandos

docker compose -f docker-compose.dev.yaml exec web bash
cat /etc/hosts
docker compose -f docker-compose.dev.yaml logs nginx
docker compose -f docker-compose.dev.yaml --profile nginx --profile debug up
docker compose -f docker-compose.dev.yaml --profile nginx up
docker compose -f docker-compose.dev.yaml --profile debug up

# override

export COMPOSE_FILE=docker-compose.dev.yaml:docker-compose.override.yaml
docker compose up
ou
docker compose -f docker-compose.dev.yaml -f docker-compose.override.yaml up

docker compose -f docker-compose.dev.yaml -f docker-compose.override.yaml config

docker compose -f docker-compose.dev.yaml -p feature-xpto up
docker compose -f docker-compose.dev.yaml -p feature-xpto ps

COMPOSE_PROJECT_NAME=feature-xpto docker compose -f docker-compose.dev.yaml up

docker compose -f docker-compose.dev.yaml -p feature-xpto exec web1 bash

docker compose -f docker-compose.dev.yaml --profile nginx up
docker compose -f docker-compose.dev.yaml cp nginx:/etc/nginx ./nginx
docker compose -f docker-compose.dev.yaml cp package.json nginx:/tmp
sudo service docker restart

https://docs.docker.com/compose/how-tos/environment-variables/envvars/
