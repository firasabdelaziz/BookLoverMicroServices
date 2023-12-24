# Base image
FROM php:8.1.13-apache

# Set the working directory
WORKDIR /var/www/html

# Copy composer files and install dependencies
COPY composer.json composer.lock ./
RUN apt-get update \
    && apt-get install -y --no-install-recommends unzip libzip-dev \
    && docker-php-ext-install zip \
    && curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer \
    && composer install --no-scripts --no-autoloader --ignore-platform-reqs \
    && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

# Copy the rest of the application code
COPY . .

# Set permissions
RUN chown -R www-data:www-data /var/www/html/storage /var/www/html/bootstrap/cache

# Set up Apache
RUN a2enmod rewrite

# Expose the port
EXPOSE 80

# Start Apache
CMD ["apache2-foreground"]
