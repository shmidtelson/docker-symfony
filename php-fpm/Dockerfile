FROM php:fpm

RUN apt-get update && apt-get install -y wget git unzip \
    && pecl install xdebug \
    && docker-php-ext-enable xdebug

# Mariadb
RUN docker-php-ext-install mysqli pdo pdo_mysql

RUN mv /usr/local/etc/php/php.ini-development /usr/local/etc/php/php.ini

RUN wget https://getcomposer.org/installer -O - -q \
    | php -- --install-dir=/bin --filename=composer --quiet

RUN usermod -u 1000 www-data

EXPOSE 9000

WORKDIR /var/www/app
