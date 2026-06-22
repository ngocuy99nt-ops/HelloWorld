FROM php:7.2-apache

# Install common PHP extensions for plain PHP projects
RUN apt-get update \
    && apt-get install -y --no-install-recommends \
        libzip-dev \
        zip \
        unzip \
        git \
    && docker-php-ext-install \
        mysqli \
        pdo \
        pdo_mysql \
        zip \
    && a2enmod rewrite headers \
    && rm -rf /var/lib/apt/lists/*

WORKDIR /var/www/html

# Safer Apache/PHP permissions
RUN chown -R www-data:www-data /var/www/html