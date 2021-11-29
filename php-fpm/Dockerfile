ARG PHP_VERSION=8
FROM php:${PHP_VERSION}-fpm-alpine

RUN echo ${PHP_VERSION}

USER root
## Install basics ###################################
RUN apk update && \
    apk upgrade && \
    apk add --update \
    $PHPIZE_DEPS \
    linux-headers \
    coreutils \
    util-linux \
    shadow

## Install PHP libs ###################################
RUN apk add --no-cache \
    openssh-client \
    libmcrypt-dev \
    openldap-dev \
    freetype-dev \
    mysql-client \
    libzip-dev \
    libpng-dev \
    giflib-dev \
    jpeg-dev \
    freetype \
    jpeg-dev \
    libjpeg \
    libldap \
    libxml2-dev \
    ldb-dev \
    libpng \
    zip \
    vim \
    git \
    bash \
    su-exec \
    && docker-php-ext-install \
    mysqli \
    pdo \
    pdo_mysql \
    bcmath \
    soap \
    ldap \
    zip \
    pdo \
    pcntl \
    gd \
    && pecl install \
    mcrypt \
    xdebug \
    && docker-php-ext-enable \
    mcrypt \
    xdebug

WORKDIR /simpledocker

CMD ["php-fpm"]

EXPOSE 9000