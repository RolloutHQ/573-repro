FROM node:18.12.1-alpine
RUN echo "this is a test"
COPY --chown=node:node package.json ./
COPY --chown=node:node package.json ./
COPY --chown=node:node yarn.lock ./
COPY --chown=node:node .yarnrc.yml ./
COPY --chown=node:node .yarn ./.yarn
COPY ./app /app
RUN cd /app && yarn install

