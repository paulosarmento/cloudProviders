# publicacao

Docker Buildx e Builds Multiplataforma

Hoje aprofundei meus estudos em Docker Buildx, entendendo como criar imagens multiplataforma, gerenciar builders e otimizar builds com cache avançado.

📌 Principais aprendizados:

✅ O que é Docker Buildx
Uma extensão poderosa do docker build que permite:

Builds multiplataforma (amd64, arm64)

Ambiente de build isolado

Emulação de arquitetura com qemu

Gerenciamento avançado de cache

Docker-in-Docker

✅ Builders, Contextos e Drivers

Builder: ambiente onde o build acontece

Contexto: define qual Docker daemon será usado

Drivers:

docker: usa o daemon local (sem isolamento e sem qemu automático)

docker-container: cria um ambiente isolado com Docker-in-Docker e suporte completo a multiplataforma

✅ QEMU e Emulação
O qemu permite construir imagens para arquiteturas diferentes da do host (ex: gerar amd64 em um host arm64), tornando os builds multiplataforma possíveis e confiáveis.

✅ Criando e gerenciando builders

docker buildx create --name meu-builder --driver docker-container --use
docker buildx inspect --bootstrap
docker buildx ls

✅ Build multiplataforma

docker buildx build --platform linux/amd64,linux/arm64 -t repo/app:latest --push .

O --push é necessário porque o resultado gera um manifest list no registry.

✅ Gerenciamento de cache

Cache local:

--cache-to type=local,dest=./cache
--cache-from type=local,src=./cache

Cache remoto (registry):

--cache-to type=registry,ref=repo/app:cache,mode=max
--cache-from type=registry,ref=repo/app:cache

✅ Exemplo prático com Go (multi-stage build)
Usando builder + scratch, gerando uma imagem mínima, segura e multiplataforma para produção.

📈 Cada capítulo reforça minha base em:

Containers

Cloud Computing

Arquitetura multiplataforma

Boas práticas de build e performance

Seguimos firmes na jornada para me tornar especialista em Cloud & Containers ☁️🐳

#Docker #Buildx #DevOps #CloudComputing #Containers #MultiArch #QEMU #AprendizadoContínuo #FullCycle

# Comandos

docker buildx ls
docker buildx create --name mybuilder --driver docker-container --use
docker buildx inspect --bootstrap
docker exec -it 7e93027f99dd sh
ps aux
docker buildx build --platform linux/amd64,linux/arm64 -t paulosarmento/docker-node-latest:latest .
docker buildx build --platform linux/amd64,linux/arm64 -t paulosarmento/docker-node-latest:latest --push .
docker buildx build \  
--cache-to type=local,dest=../docker-cache \
--cache-from type=local,src=../docker-cache \
-t paulosarmento/docker-node-latest:latest .
docker buildx prune --filter=until=24h
docker buildx rm mybuilder
docker context ls
docker build -t paulosarmento/docker-go-example:latest .
