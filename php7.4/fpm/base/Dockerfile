FROM php:7.4-fpm

RUN usermod -u 2200 www-data && groupmod -g 2200 www-data

WORKDIR /data/wwwroot

ENV TZ=Asia/Shanghai
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone