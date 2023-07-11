FROM php:7.2-fpm
LABEL maintainer='aisna@protonmail.com'
# set timezome
ENV TZ=Asia/Shanghai
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone
#
# Install package and PHP Core extensions
RUN apt-get update && apt-get install -y \
        git tig lsof htop vim subversion \
        libfreetype6-dev libjpeg62-turbo-dev libpng-dev	libicu-dev libxml2-dev libmcrypt-dev libcurl4-gnutls-dev libxslt-dev libzip-dev
RUN apt-get update \
	&& pecl install mcrypt-1.0.6 \
	&& docker-php-ext-enable mcrypt \
	&& docker-php-ext-configure gd --with-freetype-dir=/usr/lib --with-png-dir=/usr/lib --with-jpeg-dir=/usr/lib \
	&& docker-php-ext-install gd \
	&& docker-php-ext-install xsl \
	&& docker-php-ext-install sockets \
        && docker-php-ext-install intl \
        && docker-php-ext-install soap\
        && docker-php-ext-install zip \
        && docker-php-ext-install mbstring \
        && docker-php-ext-install bcmath \
        && docker-php-ext-install xml \
        && docker-php-ext-install xmlrpc \
        && docker-php-ext-install curl \
        && docker-php-ext-install json \
        && docker-php-ext-install opcache \
        && docker-php-ext-install pdo_mysql \
        && docker-php-ext-install mysqli \
        && rm -r /var/lib/apt/lists/*
# && docker-php-ext-install mcrypt \ #php从7.2开始不再在源码里支持mcrypt扩展而转到pecl方式支持
#install php composer 
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

#RUN mv "$PHP_INI_DIR/php.ini-development" "$PHP_INI_DIR/php.ini"
WORKDIR /var/www/html

# Write Permission
RUN usermod -u 1000 www-data
