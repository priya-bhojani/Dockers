# dev docker for react and other front end projects
FROM node:10-alpine

# node image is already adding user and group id 1000 named node
RUN if [ -z "`getent group 1000`" ]; then \
    addgroup -g 1000 -S username; \
    fi

RUN if [ -z "`getent passwd 1000`" ]; then \
    adduser -u 1000 -S username -G username; \
    fi

RUN npm install -g create-react-app \
                   create-react-native-app \
                   react-native-cli

RUN mkdir /app

WORKDIR /app
