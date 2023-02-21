FROM php:8.1-apache


EXPOSE 80

RUN apt-get update &&\ 
    apt-get install -y libzip-dev libpng-dev libicu-dev libxml2-dev &&\
    docker-php-ext-install mysqli pdo_mysql gd intl zip soap opcache exif

RUN mkdir -p /var/www/moodledata &&\
    chown www-data:www-data /var/www/moodledata

COPY ./elearning.ikametyok.com.conf /etc/apache2/sites-enabled/

ENTRYPOINT ["docker-php-entrypoint"]

CMD ["apache2-foreground"]
