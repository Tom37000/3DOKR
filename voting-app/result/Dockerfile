FROM node:18.20-alpine

ENV NODE_ENV=production

WORKDIR /usr/src/app

COPY package*.json ./

RUN npm ci --omit=dev

USER node

COPY --chown=node:node . .

EXPOSE 8888

CMD ["node", "server.js"]