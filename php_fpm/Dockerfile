ARG PHP_VERSION
FROM php:${PHP_VERSION}-fpm

ARG TZ=UTC
ENV TZ ${TZ}
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

RUN apt-get update && apt-get install -y \
    libzip-dev \
    && docker-php-ext-install \
    pdo_mysql \
    zip \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

COPY ./php.ini /usr/local/etc/php/
COPY ./php-fpm.d/zz-docker.conf /usr/local/etc/php-fpm.d/

WORKDIR /var/www
