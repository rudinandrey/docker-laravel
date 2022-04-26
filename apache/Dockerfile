FROM php:8.1-apache

RUN apt-get update && apt-get install -y \
	git \
	curl \
	zip \
	unzip

RUN docker-php-ext-install pdo pdo_mysql

COPY config/000-default.conf /etc/apache2/sites-available/000-default.conf

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

WORKDIR /app

COPY src/index.php /app/index.php

# RUN composer create-project laravel/laravel www

# CMD ["apache2-foreground"]