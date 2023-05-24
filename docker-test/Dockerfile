FROM node:18.12.1-alpine
RUN corepack enable
RUN mkdir -p /home/node/app/node_modules
RUN chown -R node:node /home/node

WORKDIR /home/node/app

COPY --chown=node:node yarn.lock ./
COPY --chown=node:node .yarnrc.yml ./
COPY --chown=node:node .yarn ./.yarn
COPY --chown=node:node ./app ./

USER node

RUN yarn install
COPY --chown=node:node . .

EXPOSE 3000

ENTRYPOINT [ "yarn", "credentials:dev" ]

