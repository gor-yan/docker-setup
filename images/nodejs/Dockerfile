FROM node:14.21-alpine

RUN apk update \
    && apk add --no-cache bash supervisor yarn autoconf automake gcc make g++ zlib-dev

RUN npm install --global webpack webpack-cli

CMD ["/usr/bin/supervisord", "-c", "/etc/supervisord.conf"]