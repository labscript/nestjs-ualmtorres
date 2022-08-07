FROM node:16.16.0-alpine
RUN apk add --no-cache git openssh-client bash

RUN mkdir -p /home/node/app

WORKDIR /home/node/app

RUN npm config set prefix "/home/node/.npm-global"
ENV PATH="/home/node/.npm-global/bin:${PATH}"

ARG GIT_USER_NAME
ARG GIT_USER_EMAIL

RUN git config --global user.name $GIT_USER_NAME
RUN git config --global user.email $GIT_USER_EMAIL
RUN git config --global core.excludesfile /root/.gitignore

RUN npm -g install @nestjs/cli
RUN npm -g install npm-check-updates