# php/Dockerfile
FROM php:8.3-fpm

# Instalar dependências do sistema e PDO_PGSQL
RUN apt-get update && apt-get install -y \
    libpq-dev \
    libzip-dev \
    unzip \
    git \
    gcc \
    make \
    pkg-config \
    && docker-php-ext-install pdo_pgsql \
    && apt-get clean && rm -rf /var/lib/apt/lists/*

# Copiar php.ini customizado
COPY php.ini /usr/local/etc/php/php.ini

WORKDIR /var/www/html