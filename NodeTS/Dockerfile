FROM node:10-alpine

RUN npm install -g npm

RUN npm install -g typescript

RUN npm install -g ts-node

RUN npm install -g node-gyp

RUN npm install -g @nestjs/cli

RUN apk add curl bash

RUN curl --compressed -o- -L https://yarnpkg.com/install.sh | bash

RUN apk add python python-dev py2-pip autoconf automake g++ make --no-cache

RUN pip install py-bcrypt

RUN mkdir /app

WORKDIR /app
