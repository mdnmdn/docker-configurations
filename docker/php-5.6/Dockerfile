FROM php:5.6.25-apache

#ENV PHP_INI_DIR /usr/local/etc/php

RUN apt-get update \
	&& apt-get install -y libmcrypt-dev libgd-dev libxml2-dev \
	&& docker-php-ext-install gd mcrypt soap pdo_mysql \
	&& ln -s /etc/apache2/mods-available/rewrite.load /etc/apache2/mods-enabled/ \
	&& pecl install xdebug \
	&& echo "zend_extension=/usr/local/lib/php/extensions/no-debug-non-zts-20131226/xdebug.so" > /usr/local/etc/php/conf.d/ext-xdebug.ini \
	&& pecl install channel://pecl.php.net/xhprof-0.9.4 \
	&& echo "[xhprof]" > /usr/local/etc/php/conf.d/ext-xhprof.ini \
	&& echo "extension=xhprof.so" >> /usr/local/etc/php/conf.d/ext-xhprof.ini \
	&& echo "xhprof.output_dir=/var/tmp/xhprof" >> /usr/local/etc/php/conf.d/ext-xhprof.ini \
	&& mkdir /var/tmp/xhprof; chmod 777 /var/tmp/xhprof \
	&& apt-get install -y graphviz

ENV TERM linux
#ENV APACHE_CONFDIR /etc/apache2
#ENV APACHE_ENVVARS $APACHE_CONFDIR/envvars

WORKDIR /var/www/html

EXPOSE 80
CMD ["apache2-foreground"]


#docker build .