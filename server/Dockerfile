FROM node:lts-alpine@sha256:96cc8323e25c8cc6ddcb8b965e135cfd57846e8003ec0d7bcec16c5fd5f6d39f AS dependencies

WORKDIR /dependencies
COPY package*.json ./
RUN npm install

FROM node:lts-alpine@sha256:96cc8323e25c8cc6ddcb8b965e135cfd57846e8003ec0d7bcec16c5fd5f6d39f AS runtime
COPY --from=dependencies /dependencies ./
COPY server.js .

EXPOSE 8000

CMD [ "node", "server.js" ]