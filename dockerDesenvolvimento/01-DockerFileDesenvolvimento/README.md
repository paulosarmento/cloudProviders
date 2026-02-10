# publicacao

🐳 Docker — Como acelerar o boot de containers em ambientes de desenvolvimento

Hoje estudei um repositório e uma aula prática sobre como acelerar o tempo de inicialização de containers, um ponto crítico para produtividade no desenvolvimento com Docker.

📌 Motivação

Utilizar Docker no desenvolvimento traz diversos benefícios:

Desacoplar o ambiente da aplicação da máquina local

Evitar o clássico “na minha máquina funciona”

Padronizar o ambiente entre desenvolvedores

Cria

# comandos

docker build -t minha-imagem-node -f Dockerfile.dev --no-cache .
docker run -v $(pwd):/home/node/app -it minha-imagem-node
docker build -t minha-imagem-node -f Dockerfile.dev .
