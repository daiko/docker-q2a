FROM php:7.1-fpm

MAINTAINER Florestan Bredow <florestan.bredow@daiko.fr>

ENV Q2A_VERSION=1.8.0

RUN apt-get update && apt-get install -y wget unzip \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

RUN docker-php-ext-install -j$(nproc) mysqli

RUN wget https://github.com/q2a/question2answer/releases/download/v1.8.0/question2answer-${Q2A_VERSION}.zip \
    && unzip question2answer-${Q2A_VERSION}.zip \
    && rm question2answer-${Q2A_VERSION}.zip \
    && mv question2answer-${Q2A_VERSION}/* /var/www/html/ \
    && chown -R www-data:www-data /var/www/html/*

VOLUME ["/var/www/html"]
