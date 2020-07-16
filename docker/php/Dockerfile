ARG PHP_FPM_VERSION
FROM php:$PHP_FPM_VERSION

RUN apk update && apk add \
        freetype-dev \
        libjpeg-turbo-dev \
        libpng-dev \
    && docker-php-ext-configure gd \
        --with-freetype-dir=/usr/include/ \
        --with-jpeg-dir=/usr/include/ \
        --with-png-dir=/usr/include/ \
    && docker-php-ext-install -j$(nproc) gd \
    && docker-php-ext-install mysqli pdo pdo_mysql  && docker-php-ext-enable mysqli

RUN sed -i '2i\chown www-data:www-data -R /var/www/html&&chmod 755 -R /var/www/html' \
        /usr/local/bin/docker-php-entrypoint
