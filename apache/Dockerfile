FROM php:8.1-apache

RUN apt-get update && apt-get install -y \
	git \
	curl \
	zip \
	unzip

RUN docker-php-ext-install pdo pdo_mysql 

COPY config/000-default.conf /etc/apache2/sites-available/000-default.conf

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

RUN groupadd -g 1000 www
RUN useradd -u 1000 -ms /bin/bash -g www www

WORKDIR /var/www/html

COPY src /var/www/html

RUN chmod -R www-data:www-data /var/www/html