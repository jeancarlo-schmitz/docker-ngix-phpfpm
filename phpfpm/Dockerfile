# php/Dockerfile
FROM php:8.3-fpm

# Instalar dependências do sistema e pdo_pgsql
RUN apt-get update && apt-get install -y \
    libpq-dev \
    && docker-php-ext-install pdo_pgsql

WORKDIR /var/www/html