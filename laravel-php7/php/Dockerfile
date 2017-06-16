FROM php:7.1.5-alpine
MAINTAINER Lucas Nascimento <lucas@lapou.com.br>

RUN apk upgrade --update && apk add \
    freetype libpng libjpeg-turbo freetype-dev postgresql-dev libpng-dev libjpeg-turbo-dev libxml2-dev libmcrypt libmcrypt-dev \
    && docker-php-ext-configure gd \
        --with-gd \
        --with-freetype-dir=/usr/include/ \
        --with-png-dir=/usr/include/ \
        --with-jpeg-dir=/usr/include/ \
    && docker-php-ext-configure pgsql -with-pgsql=/usr/local/pgsql \
    && docker-php-ext-install pdo pdo_mysql pdo_pgsql pgsql mcrypt gd mbstring tokenizer xml

COPY www.conf /usr/local/etc/php-fpm.d/www.conf

RUN curl -sS https://getcomposer.org/installer | php \
    && mv composer.phar /usr/local/bin/composer
