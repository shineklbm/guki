# Use the latest composer version
FROM composer:latest AS composer

# Use a valid PHP version
FROM php:8.3-fpm

# Copy Composer binary
COPY --from=composer /usr/bin/composer /usr/bin/composer

# Verify installations
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
    docker-php-ext-install \
        zip \
        gd \
        mbstring \
        xmlrpc \
        gmp \
        bcmath \
        soap \
        dom \
        hash \
        iconv \
        xml \
        xsl \
        simplexml \
        mysqli \
        pdo \
        pdo_mysql \
        ctype \
        json \
        opcache \
        tokenizer && \
    php -m | grep -q 'zip'