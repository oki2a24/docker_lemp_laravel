ARG PHP_VERSION
FROM php:${PHP_VERSION}-fpm

ARG TZ=UTC
ENV TZ ${TZ}
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

RUN apt-get update && apt-get install -y \
#    libssl-dev \
#    openssl \
#    ssl-cert \
#    unzip \
    zlib1g-dev \
    && docker-php-ext-install \
    pdo_mysql \
    zip \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*
#    && a2enmod rewrite \
#    && a2enmod ssl \
#    && a2ensite default-ssl

COPY ./php.ini /usr/local/etc/php/
#COPY ./sites-available/ /etc/apache2/sites-available/
COPY ./php-fpm.d/zz-docker.conf /usr/local/etc/php-fpm.d/

WORKDIR /var/www
