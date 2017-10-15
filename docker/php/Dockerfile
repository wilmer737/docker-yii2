FROM php:7.1-fpm

RUN apt-get update \
    && apt-get install -y \
        libmagickwand-dev \
    && rm -rf /var/lib/apt/lists/* \
    && pecl install imagick-beta \
    && echo "extension=imagick.so" > /usr/local/etc/php/conf.d/ext-imagick.ini \
    && apt-get remove -y \
        libmagickwand-dev \
    && apt-get install -y \
        libmagickwand-6.q16-2 \
    && apt-get autoremove -y

RUN apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*
