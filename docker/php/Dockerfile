FROM php:7.3.9-fpm-alpine3.10
 
RUN docker-php-ext-install mysqli pdo pdo_mysql && docker-php-ext-enable mysqli

RUN sed -i '2i\chown www-data:www-data -R /var/www/html&&chmod 755 -R /var/www/html' \
        /usr/local/bin/docker-php-entrypoint
