# Based on official PHP image with Apache
FROM php:8.2-apache

# Customize PHP modules
RUN apt-get update && apt-get install -y \
        imagemagick \
        libmagickwand-dev \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libpng-dev \
        --no-install-recommends \
    && docker-php-ext-configure gd --with-freetype --with-jpeg \
    && docker-php-ext-install -j$(nproc) gd

# Imagemagick
RUN printf "\n" | pecl install imagick
RUN docker-php-ext-enable imagick

# Enable mod_rewrite
RUN a2enmod rewrite

# Enable mod_headers
RUN a2enmod headers

RUN a2enmod vhost_alias
