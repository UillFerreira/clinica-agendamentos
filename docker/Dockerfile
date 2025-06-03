FROM php:8.2-cli

# Instala dependências do sistema
RUN apt-get update && apt-get install -y \
    libpq-dev \
    unzip \
    curl \
    git \
    zip \
    && docker-php-ext-install pdo pdo_pgsql

# Instala Composer
COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

# Instala extensões Laravel úteis
RUN apt-get install -y libzip-dev && docker-php-ext-install zip

WORKDIR /var/www
