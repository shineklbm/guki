FROM composer:1.8 AS composer

# installing php:5.6-fpm
FROM php:5.6-fpm

# copy the compose file to php
COPY --from=composer /usr/bin/composer /usr/bin/composer

# just to verify
RUN composer --version && php -v

RUN set -xe; \
    apt-get update -yqq && \
    pecl channel-update pecl.php.net && \
    apt-get install -yqq \
    git \
    apt-utils \
    libzip-dev zip unzip && \
    docker-php-ext-configure zip --with-libzip && \
    docker-php-ext-install zip && \
    php -m | grep -q 'zip'