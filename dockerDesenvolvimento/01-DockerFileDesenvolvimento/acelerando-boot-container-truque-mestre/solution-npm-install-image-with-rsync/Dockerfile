FROM node:18.18.2-slim

RUN apt update && apt install -y bc rsync

USER node

RUN mkdir /home/node/cache

WORKDIR /home/node/cache

## cache strategy
COPY --chown=node:node ./nest/package*.json ./
# demora nesta linha aqui o rsync
RUN npm install --legacy-peer-deps
## ja tem cache no container
RUN mkdir /home/node/app

WORKDIR /home/node/app

COPY start.sh /

CMD ["/start.sh"]

## build strategy
# Esta solucao ideal para pessoal que tem hardware muito distinto 