FROM node:10

RUN mkdir -p /home/node/app/node_modules && chown -R node:node /home/node/app

WORKDIR /home/node/app

COPY nodejsapp/package*.json ./

RUN npm install

COPY nodejsapp ./

COPY --chown=node:node . .

USER node

EXPOSE 8085

CMD [ "node", "app.js" ]
