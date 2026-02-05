### 📌 Publicação 1 – Introdução ao Docker (Manipulando Containers)

Hoje comecei oficialmente meus estudos em **Cloud Computing**, iniciando pelo **Docker** 🚀

Aprendi os primeiros conceitos práticos sobre manipulação de containers, como:

✅ Executar meu primeiro container

`docker run hello-world`

✅ Criar containers com nome personalizado

`docker run --name mynginx nginx`

✅ Rodar containers em segundo plano (detached)

`docker run -d nginx`

✅ Mapear portas para acessar aplicações no navegador

`docker run -d -p 8080:80 nginx`

✅ Listar, parar e remover containers

- `docker ps`
- `docker stop`
- `docker rm -f`

✅ Acessar o container via terminal

`docker exec -it mynginx bash`

Também entendi a diferença entre:

- **docker run** → cria um novo container
- **docker exec** → executa comandos em um container já rodando
- **docker attach** → conecta ao processo principal do container

Pequenos passos, mas fundamentais para construir uma base sólida em Cloud ☁️

Meu foco é aprender de forma prática e consistente todos os dias.

Se você também está estudando Docker ou Cloud, vamos trocar experiências 💬

#Docker #CloudComputing #DevOps #AprendizadoContínuo #Tecnologia #Estudos #Linux #Infraestrutura #AWS #CarreiraTech

docker tutorial
https://github.com/codeedu/wsl2-docker-quickstart/blob/main/README.md
https://docs.docker.com/engine/install/ubuntu/
