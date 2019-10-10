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
    curl \
    libssl-dev \
    libpng-dev \
    libjpeg-dev \
    libfreetype6-dev \
    apt-utils \
    zlib1g-dev \
    libzip-dev zip unzip && \
    docker-php-ext-configure zip --with-libzip && \
    docker-php-ext-install zip && \
    docker-php-ext-install gd && \
    docker-php-ext-install mysqli && \
    php -m | grep -q 'zip'