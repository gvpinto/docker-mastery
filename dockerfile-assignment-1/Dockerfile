# use this empty Dockerfile to build your assignment
FROM node:6-alpine

# NOTE: The instructions are now in the README.md file in this directory.
RUN apk add --no-cache tini

RUN mkdir -p /usr/src/app

WORKDIR /usr/src/app

COPY package.json .

RUN npm install \
    && npm cache clean --force

COPY . .

EXPOSE 3000

CMD ["/sbin/tini", "--",  "node", "./bin/www"]

