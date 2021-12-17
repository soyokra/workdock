ARG PHP_VERSION=7.4.10

FROM php:${PHP_VERSION}-fpm

LABEL maintainer="pingink <pingink@163.com>"

# base
RUN rm -rf /usr/local/etc/php-fpm.d/www.conf
RUN docker-php-ext-install mysqli pdo pdo_mysql opcache bcmath sockets
RUN pecl install redis && docker-php-ext-enable redis

# zip
RUN apt-get update && apt-get install -y \
    libzip-dev \
    unzip \
  && docker-php-ext-install zip

#gd
RUN apt-get update && apt-get install -y \
    zlib1g-dev \
    libwebp-dev  \
    libxpm-dev \
    libfreetype6-dev \
    libjpeg62-turbo-dev \
    libpng-dev \
  && docker-php-ext-configure gd --with-freetype --with-jpeg \
  && docker-php-ext-install -j$(nproc) gd

# composer
RUN curl -sS https://getcomposer.org/installer | php && mv composer.phar /usr/bin/composer && chmod u+x /usr/bin/composer && composer config -g repo.packagist composer https://mirrors.aliyun.com/composer/

EXPOSE 9000

CMD ["php-fpm", "-R"]
