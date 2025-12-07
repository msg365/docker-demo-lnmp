from php:7.3.33-fpm

RUN apt-get update && apt-get install -y \
		libfreetype-dev \
		libjpeg62-turbo-dev \
		libpng-dev \
	&& docker-php-ext-configure gd \
	&& docker-php-ext-install -j$(nproc) gd

RUN apt-get update && apt-get install -y libmemcached-dev libssl-dev zlib1g-dev \
	&& pecl install memcached-3.2.0 \
	&& docker-php-ext-enable memcached

RUN docker-php-ext-install mysqli pdo pdo_mysql && docker-php-ext-enable mysqli