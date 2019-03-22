FROM php:7-fpm

COPY --from=composer:1.8 /usr/bin/composer /usr/local/bin/composer

RUN apt-get update && apt-get install -y \
        git \
        libzip-dev \
        zip

RUN docker-php-ext-install zip

RUN pecl install mongodb-1.5.3

RUN docker-php-ext-enable mongodb

RUN mkdir /usr/src/app

WORKDIR /usr/src/app
