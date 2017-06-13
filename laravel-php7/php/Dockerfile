FROM php:7.0-fpm
MAINTAINER Lucas Nascimento <lucas@lapou.com.br>

RUN apt-get update && apt-get install -y \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libmcrypt-dev \
        libpng12-dev \
        autoconf \
        build-base \
        curl nano \
        git \
    && docker-php-ext-install -j$(nproc) iconv mcrypt mysqli \
    && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
    && docker-php-ext-install -j$(nproc) gd
   
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer \

COPY www.conf /usr/local/etc/php-fpm.d/www.conf

COPY app/ /app

RUN cd /app && \
    composer install --no-interaction
