FROM php:7.0-apache
MAINTAINER Sajivan JOSEPH-PETRICK josephpetrick.sajivan@gmail.com

RUN curl -sS https://getcomposer.org/installer | \
    php -- --install-dir=/usr/bin/ --filename=composer

RUN apt-get update
RUN apt-get install -y git
RUN docker-php-ext-install mbstring
RUN docker-php-ext-install pdo pdo_mysql
RUN apt-get install -y zlib1g-dev libicu-dev g++
RUN docker-php-ext-configure intl
RUN docker-php-ext-install intl
RUN pecl install apcu
RUN apt-get install -y zlib1g-dev \
    && docker-php-ext-install zip
COPY php.ini /usr/local/etc/php