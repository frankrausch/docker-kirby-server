# Based on official PHP image with Apache
FROM php:7.4-apache

# Customize PHP modules
RUN apt-get update && apt-get install -y \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libpng-dev \
    && docker-php-ext-configure gd --with-freetype --with-jpeg \
    && docker-php-ext-install -j$(nproc) gd

# Enable mod_rewrite
RUN a2enmod rewrite

# Enable mod_headers
RUN a2enmod headers

RUN a2enmod vhost_alias