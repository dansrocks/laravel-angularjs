FROM php:7.3-fpm-alpine

RUN apk update \
    && apk upgrade \
    && apk add --no-cache libpng-dev libjpeg-turbo-dev freetype-dev icu-dev libintl \
    && docker-php-ext-configure gd --with-gd --enable-gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ --with-png-dir=/usr/include/ \
    && docker-php-ext-configure intl --enable-intl \
    && docker-php-ext-install -j$(nproc) gd intl pdo pdo_mysql mysqli bcmath \
    && apk del --no-cache libpng-dev libjpeg-turbo-dev freetype-dev icu-dev libintl

EXPOSE 9000

CMD [ "php-fpm" ]



