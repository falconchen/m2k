ARG PHP_FPM_VERSION=8.2.14
FROM falconchen/php-fpm:${PHP_FPM_VERSION}

RUN cd /usr/local/etc/php/ \
&& cp php.ini-development php.ini \
&& echo 'alias ll="ls -la"' | tee /root/.bashrc \
&& composer global require laravel/installer \ 
&& apt update && apt install -y vim lsof\
&& apt-get clean \
&& rm -rf /var/lib/apt/lists/*

ENV PATH="/root/.config/composer/vendor/laravel/installer/bin:${PATH}"