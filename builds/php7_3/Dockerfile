FROM composer:1.8 AS composer

# installing php7.3.x
FROM php:7.3-fpm

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
    libgmp-dev \
    libxml2-dev \
    libfreetype6-dev \
    apt-utils \
    zlib1g-dev \
    libzip-dev zip unzip && \
    docker-php-ext-configure zip --with-libzip && \
    docker-php-ext-install zip && \
    docker-php-ext-install gd && \
    docker-php-ext-install mbstring && \
    docker-php-ext-install xmlrpc && \
    docker-php-ext-install gmp && \
    docker-php-ext-install bcmath && \
    docker-php-ext-install soap && \
    docker-php-ext-install dom && \
    docker-php-ext-install hash && \
    docker-php-ext-install iconv && \
    docker-php-ext-install xml && \
    docker-php-ext-install xml && \
    docker-php-ext-install xsl && \
    docker-php-ext-install simplexml && \
    docker-php-ext-install mysqli && \
    docker-php-ext-install pdo && \
    docker-php-ext-install openssl && \
    docker-php-ext-install pdo_mysql && \
    docker-php-ext-install ctype && \
    docker-php-ext-install json && \
    docker-php-ext-install opcache && \
    docker-php-ext-install tokenizer && \
    php -m | grep -q 'zip'