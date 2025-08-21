# php/Dockerfile
FROM php:8.3-fpm

# Instalar dependências do sistema necessárias para compilar extensões
RUN apt-get update && apt-get install -y --no-install-recommends \
    libpq-dev \
    libpq5 \
    libc-dev \
    libzip-dev \
    unzip \
    git \
    gcc \
    make \
    pkg-config \
    ca-certificates \
    apt-transport-https \
    && docker-php-ext-install pdo_pgsql \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

# Copiar php.ini customizado
COPY php.ini /usr/local/etc/php/php.ini

WORKDIR /var/www/html