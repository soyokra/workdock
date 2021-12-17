ARG PHP_VERSION=7.3.24

FROM php:${PHP_VERSION}

LABEL maintainer="pingink <pingink@163.com>"

##ext: default, docker-php-ext-install, pecl,  configure && install

# base
RUN docker-php-ext-install mysqli pdo pdo_mysql opcache bcmath sockets

## redis
RUN pecl install redis && docker-php-ext-enable redis

# zip
RUN apt-get update && apt-get install -y \
    libzip-dev \
    unzip \
  && docker-php-ext-install zip

#gd
RUN apt-get update -y && apt-get install -y \
    zlib1g-dev \
    libxpm-dev \
    libwebp-dev \
    libjpeg62-turbo-dev \
    libpng-dev \
    libfreetype6-dev \
  && docker-php-ext-configure gd --with-gd --with-webp-dir --with-jpeg-dir --with-png-dir --with-zlib-dir --with-xpm-dir --with-freetype-dir \
  && docker-php-ext-install gd

# mongodb
RUN pecl install mongodb && docker-php-ext-enable mongodb

# supervisor
RUN apt-get install -y supervisor
RUN rm -rf /etc/supervisord.conf
COPY supervisord.conf /etc/supervisord.conf

CMD ["/usr/bin/supervisord", "-n", "-c",  "/etc/supervisord.conf"]

