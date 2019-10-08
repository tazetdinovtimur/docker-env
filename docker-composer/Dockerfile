FROM php:7.2-cli

COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

RUN apt-get update && apt-get install -y \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libpng-dev \
        zlib1g-dev \
        libzip-dev \
        git

RUN pecl install igbinary \
    && docker-php-ext-enable igbinary

RUN docker-php-ext-install mbstring
RUN docker-php-ext-install zip
RUN docker-php-ext-configure gd --with-gd --with-jpeg-dir \
    --with-png-dir --with-zlib-dir --with-freetype-dir \
    --enable-gd-native-ttf

RUN docker-php-ext-install gd \
    && docker-php-ext-install pcntl

WORKDIR /app

ENTRYPOINT []

CMD [ "/bin/bash" ]