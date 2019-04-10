FROM php:7.3.4-fpm-alpine3.9

RUN apk update; \
    apk upgrade;
# requirement for mcrypt
RUN apk add libmcrypt-dev; \
    apk add readline-dev;

RUN apk update; \
    apk upgrade;
RUN apk add --no-cache $PHPIZE_DEPS \
    && pecl channel-update pecl.php.net \
    && pecl install xdebug-2.7.1 \
    && docker-php-ext-enable xdebug \
    && pecl install redis-4.3.0 \
    && docker-php-ext-enable redis \
    && pecl install mcrypt-1.0.2 \
    && docker-php-ext-enable mcrypt

RUN docker-php-ext-install mysqli \
    pdo_mysql