FROM php:5.6-apache

RUN apt-get update && apt-get install -y zlib1g-dev libicu-dev g++ libfreetype6-dev libjpeg62-turbo-dev  libmcrypt-dev libpng12-dev libjpeg-dev
RUN docker-php-ext-install pdo pdo_mysql
RUN docker-php-ext-install pdo mysqli
RUN docker-php-ext-install intl
RUN docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/  --with-png-dir=/usr
RUN docker-php-ext-install gd


RUN usermod -u 1000 www-data

# Définir ici la copie des fichiers si il existe seulement
ADD ./config/apache/sites-available/*.conf /etc/apache2/sites-available/*.conf
# Enable Apache mod_rewrite
RUN a2enmod rewrite

# Enable ssl folder
#RUN a2enmod ssl
