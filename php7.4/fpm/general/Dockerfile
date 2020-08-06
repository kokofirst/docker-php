FROM php:7.4-fpm

RUN apt-get update \
    && apt-get install -y build-essential \
	&& :\
	&& apt-get install --assume-yes apt-utils \
	&& :\
	&& apt-get install -y libmagickcore-dev libmagickwand-dev imagemagick libfreetype6-dev libjpeg62-turbo-dev libpng-dev \
	&& docker-php-ext-configure gd  --with-webp=/usr/include/webp --with-jpeg=/usr/include --with-freetype=/usr/include/freetype2/ \
	&& docker-php-ext-install -j$(nproc) gd \
	&& pecl install imagick \
	&& docker-php-ext-enable imagick \
	&& :\
	&& apt-get install -y libicu-dev \
	&& docker-php-ext-install -j$(nproc) intl \
    && :\
    && apt-get install -y libbz2-dev \
    && docker-php-ext-install -j$(nproc) bz2 \
	&& :\
	&& apt-get install -y libzip-dev \
	&& docker-php-ext-install -j$(nproc) zip \
	&& :\
	&& apt-get install -y libxml2-dev libxslt-dev \
	&& docker-php-ext-install -j$(nproc) soap \
	                                     xsl \
										 xmlrpc \
										 wddx \
	&& :\
	&& docker-php-ext-install -j$(nproc) iconv \
                                         pdo_mysql \
										 mysqli \
										 bcmath \
										 calendar \
										 exif \
										 gettext \
										 sockets \
										 dba \
										 pcntl \
										 shmop \
										 sysvmsg \
										 sysvsem \
										 sysvshm \
										 mbstring \
	&& :\
	&& apt-get install -y libmcrypt-dev \
	&& pecl install mcrypt \
	&& docker-php-ext-enable mcrypt \
	&& :\
	&& pecl install redis \
    && docker-php-ext-enable redis \
	&& :\
	#&& apt-get install -y libmemcached-dev zlib1g-dev \
    #&& pecl install memcached \
    #&& docker-php-ext-enable memcached \
	#&& :\
	&& apt-get install -y librabbitmq-dev \
	&& pecl install amqp \
	&& docker-php-ext-enable amqp