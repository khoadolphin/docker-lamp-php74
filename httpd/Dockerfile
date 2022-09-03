FROM php:7.4-apache

RUN apt update && apt-get -y install wget zip unzip git

ADD https://github.com/mlocati/docker-php-extension-installer/releases/latest/download/install-php-extensions /usr/local/bin/
RUN chmod +x /usr/local/bin/install-php-extensions && \
    install-php-extensions gd gmp exif @composer 
RUN docker-php-ext-install mysqli pdo pdo_mysql && docker-php-ext-enable pdo_mysql

RUN echo "ServerName localhost" >> /etc/apache2/apache2.conf
RUN a2enmod rewrite

ADD ./httpd/000-default.conf /etc/apache2/sites-available/000-default.conf
ADD ./httpd/httpd.conf /usr/local/apache2/conf/httpd.conf

RUN mkdir -p /app && rm -fr /var/www/html && ln -s /app /var/www/html

WORKDIR /app
