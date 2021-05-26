FROM php:7.4-fpm

RUN apt-get update \
    && apt-get install -y wget \
    nano \
    vim \
    git \
    unzip \
    zip \
    imagemagick \
    nodejs \
    npm \
    mariadb-server \
    mariadb-client \
    curl \
    zlib1g-dev \
    libxml2-dev \
    libpng-dev \
    libzip-dev \
    libpq-dev \
    libicu-dev \
    libjpeg-dev \
    libfreetype6-dev \
    debconf subversion apt-transport-https apt-utils \
    build-essential locales acl mailutils \
    gnupg gnupg1 gnupg2 \
    sudo \
    ssh \
    && pecl install xdebug \
    && docker-php-ext-install \
    pdo_mysql \
    mbstring \
    pdo \
    soap \
    zip \
    opache \
    gd \
    intl \
    && docker-php-ext-enable -j5 gd mbstring mysqli pdo pdo_mysql shmop

ADD ./php.ini /usr/local/etc/php/php.ini

RUN wget https://getcomposer.org/installer -O - -q \
    | php -- --install-dir=/bin --filename=composer --quiet

WORKDIR /var/www
