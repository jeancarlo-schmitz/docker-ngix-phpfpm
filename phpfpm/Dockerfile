FROM php:8.3-fpm-bookworm

# Ajustar repositórios para https + instalar dependências
RUN printf '%s\n' \
    "deb https://deb.debian.org/debian bookworm main contrib non-free-firmware" \
    "deb https://deb.debian.org/debian-security bookworm-security main contrib non-free-firmware" \
    "deb https://deb.debian.org/debian bookworm-updates main contrib non-free-firmware" \
    > /etc/apt/sources.list \
    && apt-get update \
    && apt-get install -y --no-install-recommends \
        apt-transport-https \
        ca-certificates \
        libpq-dev \
        libzip-dev \
        unzip \
        git \
        gcc \
        make \
        pkg-config \
    && docker-php-ext-install pdo_pgsql \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

# Copiar php.ini customizado
COPY php.ini /usr/local/etc/php/php.ini

# Definir diretório de trabalho
WORKDIR /var/www/html