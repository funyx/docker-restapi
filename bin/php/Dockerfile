FROM php:7.3.4-fpm-alpine3.9

ARG USE_XDEBUG

RUN apk update; \
    apk upgrade;

# requirement for mcrypt
RUN apk add libmcrypt-dev; \
    apk add readline-dev;

RUN apk update; \
    apk upgrade;

RUN apk add --no-cache $PHPIZE_DEPS \
    && pecl channel-update pecl.php.net \
    && pecl install redis-4.3.0 \
    && docker-php-ext-enable redis \
    && pecl install mcrypt-1.0.2 \
    && docker-php-ext-enable mcrypt

RUN if [ "${USE_XDEBUG}" == "true" ]; \
    then \
        pecl install xdebug-2.7.1 \
        && docker-php-ext-enable xdebug; \
    fi;

# add the xdebug ini config (used only if xdebug is enabled)
ADD docker-php-ext-xdebug-config.ini /usr/local/etc/php/conf.d/docker-php-ext-xdebug-config.ini

RUN docker-php-ext-install mysqli \
    pdo_mysql