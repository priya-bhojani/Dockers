FROM php:7.4-cli
  
LABEL phpdevelop-dockerfile=PHPDEVELOP

# prepare php ini settings
RUN mkdir /usr/src/php
RUN tar --file /usr/src/php.tar.xz --extract --strip-components=1 --directory /usr/src/php
RUN cp /usr/src/php/php.ini-development /usr/local/etc/php/php.ini

# add composer
COPY --from=composer:1.9 /usr/bin/composer /usr/local/bin/composer

# add git, wget, zip
RUN apt-get update \
  && apt-get install -y \
        curl \
        git \
        wget \
        libzip-dev \
        zip
RUN docker-php-ext-configure zip
RUN docker-php-ext-install zip

# BC Math extension
RUN docker-php-ext-install bcmath

# Mongo DB
RUN pecl install mongodb-1.7.2
RUN docker-php-ext-enable mongodb

# Install and setup xDebug
RUN pecl install xdebug-2.8.1 \
    && docker-php-ext-enable xdebug \
    && echo "xdebug.remote_enable=1" >> /usr/local/etc/php/php.ini \
    && echo 'xdebug.remote_port=9000' >> /usr/local/etc/php/php.ini \
    && echo 'xdebug.remote_connect_back=1' >> /usr/local/etc/php/php.ini

# Remove install files
RUN rm -rf /var/lib/apt/lists/*

# Symfony FW
RUN wget https://get.symfony.com/cli/installer -O - | bash
RUN mv /root/.symfony/bin/symfony /usr/local/bin/symfony

# PHP CS Fixer
RUN wget https://cs.symfony.com/download/php-cs-fixer-v2.phar -O php-cs-fixer
RUN chmod a+x php-cs-fixer
RUN mv php-cs-fixer /usr/local/bin/php-cs-fixer

# PHP Infection
RUN wget https://github.com/infection/infection/releases/download/0.10.3/infection.phar -O infection
RUN chmod +x infection
RUN mv infection /usr/local/bin/infection

# prepare workdir
RUN mkdir -p /usr/src/app;
WORKDIR /usr/src/app
