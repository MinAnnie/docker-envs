FROM node:22-alpine3.18

RUN addgroup -S appgroup && adduser -S appuser -G appgroup

USER root

RUN npm install -g @angular/cli@17.3.7

LABEL authors="angie"

RUN apk add --update --no-cache \
    git \
    neovim

USER appuser
USER root
USER appuser

WORKDIR /usr/src/app

EXPOSE 4200
