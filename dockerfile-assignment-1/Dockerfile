# use this empty Dockerfile to build your assignment

# NOTE: The instructions are now in the README.md file in this directory.
FROM node:23-alpine

EXPOSE 3000

RUN apk add --update \
  tini

RUN mkdir -p /usr/src/app

WORKDIR /usr/src/app

COPY package.json package.json

RUN npm install -g npm@10.9.1
RUN npm install
RUN npm cache clean --force

COPY . .

CMD [ "tini", "--", "node", "./bin/www"]
