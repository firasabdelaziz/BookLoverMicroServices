FROM php:8.1-fpm

RUN apt-get update && \
    apt-get install -y libcurl4-openssl-dev nginx pkg-config libssl-dev && \
    apt-get install -y libpng-dev && \
    apt-get install -y libmcrypt-dev && \
    apt-get install -y default-mysql-client && \
    docker-php-ext-install pdo_mysql && \
    docker-php-ext-install gd && \
    pecl install mongodb && \
    apt-get install -y libxslt-dev && \
    docker-php-ext-install xsl && \
    apt-get update && \
    apt-get install -y git && \
    apt-get install -y unzip && \
    apt-get install -y zip && \
    apt-get install -y libzip-dev && \
    docker-php-ext-install zip && \
    apt-get install -y libicu-dev && \
    docker-php-ext-install intl && \
    curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/bin/ --filename=composer && \
    docker-php-ext-install bcmath && \
    apt-get install -y supervisor

ADD php.ini /usr/local/etc/php


COPY . /var/www
RUN ln -sf /dev/stdout /var/log/nginx/access.log


WORKDIR /var/www


