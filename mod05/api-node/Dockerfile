FROM node:19.6-alpine

WORKDIR /usr/src/app

ENV NODE_ENV=production

COPY package*.json ./ 

RUN --mount=type=cache,target=/user/src/app/.npm \
  npm set cache /user/src/app/.npm && \
  npm ci --only=production 

USER node

COPY --chown=node:node ./src .

CMD ["node", "index.js"]

