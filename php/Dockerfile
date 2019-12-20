FROM php:7.3-fpm

RUN apt-get update -y \
	&& apt-get install libzip-dev zip libmemcached-dev  -y \
    && apt-get install vim -y \
    && apt-get install htop \
    && docker-php-ext-configure opcache --enable-opcache \
    && docker-php-ext-install zip opcache \
    && docker-php-ext-configure opcache --enable-mysqli \
    && docker-php-ext-install mysqli \
    && docker-php-ext-configure opcache --enable-pdo_mysql \
    && docker-php-ext-install pdo_mysql \
    && pecl install memcached \
    && rm -rf /var/lib/apt/lists/*

ADD ./php.ini /usr/local/etc/php/php.ini

EXPOSE 9000