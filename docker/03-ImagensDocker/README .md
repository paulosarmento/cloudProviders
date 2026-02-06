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

---

Dockerfile, boas práticas e otimização de imagens

Hoje avancei mais um capítulo nos meus estudos em Docker e aprendi conceitos fundamentais para construir imagens mais eficientes, seguras e profissionais.

📌 Principais aprendizados:

✅ Estrutura de um Dockerfile
Entendi o papel das principais instruções:

FROM, ARG, RUN, ENV, WORKDIR

COPY, CMD e ENTRYPOINT

EXPOSE, HEALTHCHECK, USER e LABEL

✅ Uso inteligente de cache
Separar:

COPY package\*.json ./
RUN npm install
COPY . .

permite reaproveitar cache e acelerar builds.

✅ Importância do .dockerignore
Evitar enviar arquivos desnecessários como:

node_modules

.git

logs

Dockerfile

Reduzindo tamanho e tempo de build.

✅ Segurança
Rodar containers com usuário não root usando:

USER 1001

✅ Multi-stage build (Go)
Construir a aplicação em uma imagem completa e gerar uma imagem final mínima com scratch, trazendo:

Menor tamanho

Mais segurança

Melhor performance

✅ Diferença entre CMD e ENTRYPOINT

CMD: pode ser sobrescrito

ENTRYPOINT: define o executável principal

✅ HEALTHCHECK
Criar endpoint /health para monitorar se a aplicação está funcionando corretamente.

📈 Cada capítulo reforça minha base para atuar com containers e cloud de forma profissional.

Seguimos firmes na jornada para me tornar especialista em Cloud & Containers ☁️🐳

#Docker #CloudComputing #DevOps #Containers #Dockerfile #AprendizadoContínuo #FullCycle #Estudos
