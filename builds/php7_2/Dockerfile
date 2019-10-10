FROM composer:1.9 AS composer19

# installing php7.1.x
FROM php:7.2-fpm

# copy the compose file to php
COPY --from=composer19 /usr/bin/composer /usr/bin/composer

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