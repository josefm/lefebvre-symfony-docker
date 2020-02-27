FROM php:7.4.2-fpm-buster
ARG TIMEZONE

RUN echo 'alias sf="php bin/console"' >> ~/.bashrc

RUN apt-get update && apt-get install -y \
    openssl \
    git \
    unzip \
    zlib1g-dev \
    libzip-dev \
    libpng-dev \
    vim 

# Set timezone
RUN ln -snf /usr/share/zoneinfo/${TIMEZONE} /etc/localtime && echo ${TIMEZONE} > /etc/timezone \
    && printf '[PHP]\ndate.timezone = "%s"\n', ${TIMEZONE} > /usr/local/etc/php/conf.d/tzone.ini \
    && "date"

RUN echo 'memory_limit = 1024M' >> /usr/local/etc/php/conf.d/docker-php-config.ini \
    && echo 'opcache.enable=1' >> /usr/local/etc/php/conf.d/docker-php-config.ini \
    && echo 'opcache.revalidate_freq=10' >> /usr/local/etc/php/conf.d/docker-php-config.ini \
    && echo 'opcache.validate_timestamps=1' >> /usr/local/etc/php/conf.d/docker-php-config.ini \
    && echo 'opcache.max_accelerated_files=10000' >> /usr/local/etc/php/conf.d/docker-php-config.ini \
    && echo 'opcache.memory_consumption=192' >> /usr/local/etc/php/conf.d/docker-php-config.ini \
    && echo 'opcache.max_wasted_percentage=10' >> /usr/local/etc/php/conf.d/docker-php-config.ini \
    && echo 'opcache.interned_strings_buffer=1' >> /usr/local/etc/php/conf.d/docker-php-config.ini \
    && echo 'opcache.fast_shutdown=1' >> /usr/local/etc/php/conf.d/docker-php-config.ini

RUN docker-php-ext-install pdo pdo_mysql zip gd opcache

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer \
    && composer --version

WORKDIR /var/www/symfony

COPY . /var/www/symfony
# RUN composer install