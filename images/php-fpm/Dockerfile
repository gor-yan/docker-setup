FROM php:8.2-fpm

RUN apt-get update \
  && apt-get install -y --no-install-recommends \
    git \
    sqlite3 \
    libsqlite3-dev \
    curl \
    pkg-config \
    libssl-dev \
    libmemcached-dev \
    libcurl4-openssl-dev \
    libz-dev \
    libzip-dev \
    libpq-dev \
    libjpeg-dev \
    libpng-dev \
    libldb-dev \
    libedit-dev \
    libldap2-dev \
    libxml2-dev \
    libfreetype6-dev \
    libssl-dev \
    libxslt-dev \
  && rm -rf /var/lib/apt/lists/* \

RUN && docker-php-ext-install zip \
    && docker-php-ext-install ftp \
    && docker-php-ext-install pcntl

RUN pecl install xdebug

CMD ["php-fpm"]