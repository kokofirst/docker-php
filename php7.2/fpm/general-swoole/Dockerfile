FROM kokofirst/docker-php:7.2-fpm-general

RUN pecl install -o -f swoole \
    && docker-php-ext-enable swoole