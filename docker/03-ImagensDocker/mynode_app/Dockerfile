ARG NODE_VERSION=20.10.0
FROM node:${NODE_VERSION}

ENV PORT=3001
ENV MESSAGE="Hello Docker!"

WORKDIR /usr/src/app

COPY package*.json ./
RUN npm install
COPY . .

RUN useradd -m mynode
USER mynode


HEALTHCHECK --interval=10s --timeout=5s --start-period=5s --retries=3 \
    CMD [ "curl","-f","http://localhost:3001" ]

CMD [ "node", "index.js" ]