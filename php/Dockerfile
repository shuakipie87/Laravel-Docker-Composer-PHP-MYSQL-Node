ARG PHP_VERSION=8.3
FROM php:${PHP_VERSION}-fpm

RUN apt-get update && apt-get install -y \
    git curl libpng-dev libonig-dev libxml2-dev zip unzip nodejs npm \
    && docker-php-ext-install pdo_mysql mbstring exif pcntl bcmath gd \
    && apt-get clean && rm -rf /var/lib/apt/lists/*

COPY --from=composer:latest /usr/bin/composer /usr/bin/composer
WORKDIR /var/www
COPY . .
RUN chown -R www-data:www-data /var/www && chmod -R 755 /var/www
EXPOSE 9000
CMD ["php-fpm"]
