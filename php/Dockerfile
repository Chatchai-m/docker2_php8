ARG PHP_VERSION=""
# FROM php:${PHP_VERSION:+${PHP_VERSION}-}fpm-alpine
FROM php:${PHP_VERSION}-fpm

RUN apt update; \ 
    apt -y upgrade; \
    pecl install trader; \
    docker-php-ext-enable trader; \
    apt install -y libzip-dev zip nano tree; \
    apt install -y libfreetype6-dev libjpeg62-turbo-dev libpng-dev \
	&& docker-php-ext-configure gd --with-freetype --with-jpeg \
	&& docker-php-ext-install -j$(nproc) gd

RUN docker-php-ext-install mysqli pdo pdo_mysql zip
#  bz2 bcmath sockets gd gettext gmp intl ldap pgsql shmop soap 
