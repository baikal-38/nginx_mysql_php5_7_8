#https://github.com/rhamdeew/docker-php-8-fpm-alpine/blob/master/Dockerfile

FROM php:8.3-fpm-alpine

COPY --from=composer/composer:latest-bin /composer /usr/bin/composer

#эту строку можно раскомментировать, если на сервере есть доступ к Интернету
#RUN apk add --no-cache mysql-client msmtp perl wget procps shadow libzip libpng libjpeg-turbo libwebp freetype icu icu-data-full

#эту строку можно раскомментировать, если на сервере есть доступ к Интернету
#RUN apk add --no-cache --virtual build-essentials \
#    icu-dev icu-libs zlib-dev g++ make automake autoconf libzip-dev \
#    libpng-dev libwebp-dev libjpeg-turbo-dev freetype-dev && \
#    docker-php-ext-configure gd --enable-gd --with-freetype --with-jpeg --with-webp && \
#    docker-php-ext-install gd && \
#    docker-php-ext-install mysqli && \
#    docker-php-ext-install pdo_mysql && \
#    docker-php-ext-install intl && \
#    docker-php-ext-install opcache && \
#    docker-php-ext-install exif && \
#    docker-php-ext-install zip && \
#    apk del build-essentials #&& rm -rf /usr/src/php*


#RUN wget https://getcomposer.org/composer-stable.phar -O /usr/local/bin/composer && chmod +x /usr/local/bin/composer


# Для начала указываем исходный образ, он будет использован как основа
#FROM php:8.3-fpm


# RUN выполняет идущую за ней команду в контексте нашего образа.
# В данном случае мы установим некоторые зависимости и модули PHP.
# Для установки модулей используем команду docker-php-ext-install.
# На каждый RUN создается новый слой в образе, поэтому рекомендуется объединять команды.
#RUN apt-get update && apt-get install -y \
#        curl \
#        wget \
#        git \
#        libfreetype6-dev \
#        libjpeg62-turbo-dev \
#	libpng-dev \
#	libonig-dev \
#	libzip-dev \
#	libmcrypt-dev \
#        && pecl install mcrypt-1.0.3 \
#	&& docker-php-ext-enable mcrypt \
#        && docker-php-ext-install -j$(nproc) iconv mbstring mysqli pdo_mysql zip \
#	&& docker-php-ext-configure gd --with-freetype --with-jpeg \
#        && docker-php-ext-install -j$(nproc) gd \
#        && docker-php-ext-install bcmath \
#        && docker-php-ext-install sockets

# Куда же без composer'а.
#RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer


# Добавим свой php.ini, можем в нем определять свои значения конфига
#ADD php.ini /usr/local/etc/php/conf.d/40-custom.ini

# Указываем рабочую директорию для PHP
#WORKDIR /var/www

# Запускаем контейнер
# Из документации: The main purpose of a CMD is to provide defaults for an executing container. These defaults can include an executable, 
# or they can omit the executable, in which case you must specify an ENTRYPOINT instruction as well.
#CMD ["php-fpm"]

#открываем порт для локального веб сервера PHP
#EXPOSE 80

#CMD ["php", "-S", "0.0.0.0:80"]
