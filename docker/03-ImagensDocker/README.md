# image

docker inspect nginx
docker inspect --format='{{.Id}}' nginx
docker search nginx
docker pull ubuntu
docker pull nginx:1.21
docker images prune
docker images prune -a
docker images --no-trunc
docker builder prune -a -f
docker system df

SBOM - assinar image
https://hub.docker.com/r/nginx/nginx-ingress#sbom-software-bill-of-materials

RED HAT
https://www.redhat.com/en/technologies/cloud-computing/openshift
https://quay.io/?utm_source=chatgpt.com
Escaneamento de vulnerabilidades (security scan)
Gerenciamento de permissões (quem pode puxar ou publicar imagens)

DockerHub
https://hub.docker.com/
maior catálogo de imagens públicas

Amazon ECR
https://gallery.ecr.aws/
https://docs.aws.amazon.com/pt_br/AmazonECR/latest/userguide/what-is-ecr.html

Git hub
https://github.com/orgs/github/packages?package_type=container

Azure ACR - Privado assinatura
https://azure.microsoft.com/pt-br/products/container-registry
acessa imagens dentro do seu registro ACR via Azure Portal.

Google GCR
https://docs.cloud.google.com/artifact-registry/docs/overview?hl=pt-br
precisa saber o nome do repositório para acessar as imagens.

## Build

docker build -t paulosarmento/docker-node-example:latest .
docker build --build-arg NODE_VERSION=21 -t paulosarmento/docker-node-latest:latest .
docker run -p 3001:3001 -e MESSAGE="Hello www" paulosarmento/docker-node-latest:latest
docker run -p 3001:3001 --name appnode -e MESSAGE="Hello www" paulosarmento/docker-node-latest:latest
docker run -u root -p 3001:3001 --name appnode -e MESSAGE="Hello www" paulosarmento/docker-node-latest:latest
docker images --no-trunc

## Go

Verificar arquitetura
file main
main: Mach-O 64-bit executable x86_64
go build -o main main.go

Compilar para rodar no mac
GOARCH=arm64 GOOS=darwin go build -o main main.go

docker build -t paulosarmento/docker-go-example:latest .
docker build --no-cache -t paulosarmento/docker-go-example:latest .

docker run --rm paulosarmento/docker-go-example
docker run --rm paulosarmento/docker-go-example 8081
docker run --rm -p 8080:8081 paulosarmento/docker-go-example 8081
docker inspect paulosarmento/docker-go-example
docker ps --filter "label=env=production"

- ONBUILD -> comando só roda na outra imagem top
  docker build -t paulosarmento/docker-node-base:latest -f Dockerfile.base .
  docker build -t paulosarmento/docker-node-child:latest -f Dockerfile.child .
