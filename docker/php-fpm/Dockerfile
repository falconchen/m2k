ARG PHP_FPM_VERSION=8.2.7-fpm
FROM php:${PHP_FPM_VERSION}
RUN apt update -y && apt install -y  libwebp-dev libjpeg-dev libpng-dev libfreetype6-dev zlib1g-dev curl \
    nodejs npm  && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

RUN curl -sSLf \
        -o /usr/local/bin/install-php-extensions \
        https://github.com/mlocati/docker-php-extension-installer/releases/latest/download/install-php-extensions && \
    chmod +x /usr/local/bin/install-php-extensions && \
    install-php-extensions gd mysqli zlib imagick exif zip intl pdo_mysql redis

COPY --from=composer/composer:2-bin /composer /usr/local/bin/composer
