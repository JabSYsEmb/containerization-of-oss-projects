FROM php:8.1-apache

WORKDIR /var/www/html

EXPOSE 80

 RUN apt-get update &&\
     apt-get install -y libzip-dev libpng-dev libicu-dev libxml2-dev

RUN docker-php-ext-install mysqli pdo_mysql gd intl zip soap opcache

RUN mkdir -p /var/www/moodledata &&\
    chown www-data:www-data /var/www/moodledata

# COPY ./php.ini /usr/local/etc/php/

ENTRYPOINT ["docker-php-entrypoint"]

CMD ["apache2-foreground"]
