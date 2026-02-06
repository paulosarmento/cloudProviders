📦 Docker – Imagens, Registries e Docker Hub

Hoje avancei nos estudos sobre Imagens Docker e como elas são gerenciadas e distribuídas.

Principais aprendizados:

🔹 Uma imagem Docker é um pacote imutável que contém tudo o que a aplicação precisa para rodar (código, dependências e configurações).
Os containers são instâncias criadas a partir dessas imagens.

🔹 As imagens são formadas por camadas, o que economiza espaço em disco e acelera downloads, já que camadas podem ser reutilizadas entre diferentes imagens.

🔹 Entendi a diferença entre:

Imagens oficiais (ex: nginx, redis, mysql)

Imagens de terceiros (usuario/imagem)

🔹 Aprendi a gerenciar imagens com comandos como:

docker images

docker rmi

docker inspect

docker pull

🔹 Também estudei sobre Registries, como:

Docker Hub

Amazon ECR

Google GCR

Azure ACR

E boas práticas importantes:
✔ Usar tags específicas (ex: nginx:1.21)
✔ Limpar imagens não utilizadas (docker image prune)
✔ Verificar espaço em disco (docker system df)
✔ Entender aspectos de segurança e SBOM

Esse conhecimento é fundamental para trabalhar com containers em ambientes profissionais e cloud computing ☁️
Seguimos aprendendo um pouco todos os dias 🚀

#Docker #CloudComputing #DevOps #Containers #DockerHub #Infraestrutura #AprendizadoContínuo #Tecnologia #AWS #CarreiraTech

# image

docker inspect nginx
docker inspect --format='{{.Id}}' nginx
docker search nginx
docker pull ubuntu
docker pull nginx:1.21
docker images prune
docker images prune -a
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
