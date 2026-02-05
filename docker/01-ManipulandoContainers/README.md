🚀 Iniciando meus estudos em Cloud com Docker – Manipulando Containers

Hoje avancei no meu aprendizado em Docker e estudei os principais comandos para criação e gerenciamento de containers na prática.

Principais pontos que aprendi:

✅ Executar o primeiro container
docker run hello-world

✅ Criar containers com nome personalizado e rodar em segundo plano
docker run --name mynginx nginx
docker run -d mynginx

✅ Mapear portas para acessar aplicações no navegador
docker run -d -p 8080:80 nginx

✅ Listar, parar, iniciar e remover containers
docker ps / docker ps -a
docker stop / docker start
docker rm / docker rm -f

✅ Acessar containers via terminal
docker exec -it mynginx bash

Também entendi a diferença entre:

docker run → cria um novo container

docker exec → executa comandos em um container já em execução

docker attach → conecta ao processo principal do container

Pequenos passos, mas essenciais para construir uma base sólida em Cloud Computing ☁️
Vou documentar minha evolução diariamente e compartilhar aqui meu progresso.

Se você também estuda Docker ou Cloud, vamos trocar experiências!

#Docker #CloudComputing #DevOps #Estudos #AprendizadoContínuo #Tecnologia #Linux #AWS #CarreiraTech

docker tutorial
https://github.com/codeedu/wsl2-docker-quickstart/blob/main/README.md
https://docs.docker.com/engine/install/ubuntu/
