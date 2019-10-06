FROM composer:1.9 AS composer19

# installing php7.1.x
FROM php:7.1-fpm

# copy the compose file to php
COPY --from=composer19 /usr/bin/composer /usr/bin/composer

# just to verify
RUN composer --version && php -v