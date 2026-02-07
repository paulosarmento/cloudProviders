# publicacao

Hoje finalizei mais um capítulo dos meus estudos em Docker, focado em Docker Networking 🌐🐳

Aprendi como os containers se comunicam entre si e com o host, entendendo conceitos essenciais para aplicações distribuídas e arquiteturas modernas.

Principais aprendizados:

✔ Tipos de redes: Bridge e Host
✔ Comunicação entre containers via DNS interno
✔ Integração entre Node.js e MongoDB em rede personalizada
✔ Uso do host.docker.internal
✔ Isolamento de serviços com múltiplas redes
✔ Diferenças entre Bridge vs Host (segurança, desempenho e compatibilidade)

Cada capítulo concluído é mais um passo na minha jornada para me tornar especialista em Cloud e DevOps 🚀☁️

#Docker #DockerNetworking #DevOps #Cloud #Containers #NodeJS #MongoDB #Learning #FullCycle

# comandos

docker network ls
docker network create my-network
docker run -d --name web --network my-network nginx
docker ps
docker run -d --name db --network my-network mongo
docker ps
docker exec -it web bash
apt-get update
apt-get install iputils-ping
ping db

docker build -t mynode_app_network .
docker image ls | grep node
docker run -d --name appnode --network my-network mynode_app_network:latest
docker logs appnode
docker run -d --name app --network backend-net mynode_app_network:latest
docker run -d --name db --network db-net mongo
docker network connect db-net app
docker start app
docker logs app
docker run -d --name app --network backend-net --network db-net mynode_app_network:latest

docker run -d --name nginx --network host nginx
docker run -d --name nginx nginx
node web.js
docker network inspect bridge | grep Gateway
cat etc/hosts
docker run -d --add-host=host.docker.internal:host-gateway --name nginx nginx

# comunicacao legal entre containers :)

docker run -d --add-host=host.docker.internal:host-gateway --network host --name nginx nginx
curl host.docker.internal:8080
docker run -d -p 8080:80 --name nginx2 nginx
