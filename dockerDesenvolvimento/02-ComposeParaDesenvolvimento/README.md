# comandos

docker compose -f docker-compose.dev.yaml exec web bash
cat /etc/hosts
docker compose -f docker-compose.dev.yaml logs nginx
docker compose -f docker-compose.dev.yaml --profile nginx --profile debug up
docker compose -f docker-compose.dev.yaml --profile nginx up
docker compose -f docker-compose.dev.yaml --profile debug up
