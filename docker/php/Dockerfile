FROM php:8.1-fpm-alpine

# install packages
RUN apk update && \
    apk upgrade && \
    apk add --update --no-cache \
    tzdata \
    autoconf \
    bash \
    git \
    build-base \
    curl-dev \
    icu-dev \
    freetype-dev \
    libjpeg \
    libjpeg-turbo \
    libjpeg-turbo-dev \
    libpng \
    libpng-dev \
    libxml2-dev \
    libxpm-dev \
    libxslt-dev \
    libwebp-dev \
    jpeg-dev \
    mysql-dev \
    mysql-client \
    openssl \
    py-pip \
    sudo \
    supervisor \
    vim \
    yaml-dev \
    zlib-dev \
    linux-headers \
    libzip-dev && \
    cp /usr/share/zoneinfo/Asia/Tokyo /etc/localtime

RUN docker-php-ext-install pdo_mysql mysqli

COPY --link --from=composer:latest /usr/bin/composer /usr/bin/