FROM php:8.2-cli

RUN apt-get update \
  && apt-get install -y --no-install-recommends \
    git \
    wget \
    curl \
    nano \
    openssh-client \
    supervisor \
    libzip-dev \
    libjpeg-dev \
    libpng-dev \
    sqlite3 \
    libsqlite3-dev \
    libpq-dev

RUN docker-php-ext-install zip \
    && docker-php-ext-install pdo \
    && docker-php-ext-install mysqli \
    && docker-php-ext-install gd \
    && docker-php-ext-install zip \
    && docker-php-ext-install pcntl \
    && docker-php-ext-install ftp

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

RUN curl -sL https://deb.nodesource.com/setup_18.x | bash - && \
    apt-get install -y nodejs

RUN rm -rf /var/lib/apt/lists/*

RUN useradd -m -s /bin/bash launchpad
RUN usermod -u 1000 launchpad
RUN groupmod -g 1000 launchpad

CMD ["/usr/bin/supervisord"]