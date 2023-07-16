FROM node:19.6-alpine 

WORKDIR /usr/src/app  

ENV NODE_ENV production

COPY package.json ./ 

RUN --mount=type=cache,target=/usr/src/app/.npm \
    npm set cache /usr/src/app/.npm && \
    npm install

USER node

COPY --chown=node:node . .

EXPOSE 8080

CMD ["node","index.js"]