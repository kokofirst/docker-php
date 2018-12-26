FROM php:7.3-cli

RUN usermod -u 2200 www-data && groupmod -g 2200 www-data

WORKDIR /data/wwwroot

RUN apt-get update \
    && pecl install -o -f swoole \
    && docker-php-ext-enable swoole

ENV TZ=Asia/Shanghai
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone