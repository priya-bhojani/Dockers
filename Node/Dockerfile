# dev docker for all nodejs backend and frontend (ionic|angular|react|nestjs)
FROM node:12-alpine

# node image is already adding user and group id 1000 named node
RUN if [ -z "`getent group 1000`" ]; then \
    addgroup -g 1000 -S username; \
    fi

RUN if [ -z "`getent passwd 1000`" ]; then \
    adduser -u 1000 -S username -G username; \
    fi

RUN npm install -g npm

RUN apk add curl bash

RUN curl --compressed -o- -L https://yarnpkg.com/install.sh | bash

RUN npm install -g node-gyp

RUN apk add python python-dev py2-pip autoconf automake g++ make --no-cache

RUN pip install py-bcrypt

# Hugely possible that this is not working anymore, as of typescript|ts-node 8
# RUN npm install -g typescript

# RUN npm install -g ts-node

RUN npm install -g @angular/cli

RUN npm install -g ionic

# Large and long time to install, use only when needed
# RUN npm install -g ionic cordova

RUN npm install -g create-react-app \
                   create-react-native-app \
                   react-native-cli

RUN npm install -g @nestjs/cli

RUN mkdir /app

WORKDIR /app
