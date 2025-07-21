FROM php:8.2-cli


# Optional: install extensions if needed
RUN docker-php-ext-install pdo pdo_mysql

WORKDIR /var/www/html

CMD ["php", "-S", "0.0.0.0:8000", "-t", "public"]

RUN apt-get update && apt-get install -y \
    git \
    unzip \
    zip \
    libicu-dev \
    libpq-dev \
    libzip-dev \
    libonig-dev \
    libxml2-dev \
    libcurl4-openssl-dev \
    curl \
    && docker-php-ext-install intl pdo pdo_mysql zip

# Install Composer
COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

WORKDIR /var/www/html