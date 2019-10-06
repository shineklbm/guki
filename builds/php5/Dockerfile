FROM composer:1.8 AS composer18

# installing php:5.6-fpm
FROM php:5.6-fpm

# copy the compose file to php
COPY --from=composer18 /usr/bin/composer /usr/bin/composer

# just to verify
RUN composer --version && php -v