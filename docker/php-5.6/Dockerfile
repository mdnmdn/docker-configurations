FROM php:5.6.25-apache

#ENV PHP_INI_DIR /usr/local/etc/php

RUN apt-get update && apt-get install -y libmcrypt-dev libgd-dev libxml2-dev && docker-php-ext-install gd mcrypt soap pdo_mysql

#ENV APACHE_CONFDIR /etc/apache2
#ENV APACHE_ENVVARS $APACHE_CONFDIR/envvars

WORKDIR /var/www/html

EXPOSE 80
CMD ["apache2-foreground"]