FROM php:7.0.13-apache

RUN ln -s /etc/apache2/mods-available/rewrite.load /etc/apache2/mods-enabled/; \
	apt-get update; \
    apt-get install -y htop; \
    apt-get install -y libgd-dev libxml2-dev libmcrypt-dev libxslt-dev libicu-dev; \
    docker-php-ext-install mcrypt soap xsl intl zip pdo_mysql; \
	docker-php-ext-configure gd  --with-jpeg-dir=/usr/include/ ; \
	docker-php-ext-install gd;\
    pecl install xdebug; \
    docker-php-ext-enable xdebug; 
	
#	docker-php-ext-configure gd  --with-jpeg-dir=/usr/include/  #--with-freetype-dir=/usr/include/; \

ENV TERM linux

WORKDIR /var/www/html

EXPOSE 80
CMD ["apache2-foreground"]


# docker build .
# docker tag xxx mdnmdn/php-7.0.13-apache
# docker push mdnmdn/php-7.0.13-apache