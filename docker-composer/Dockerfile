FROM php:7.2-cli

COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

RUN apt-get update
RUN apt-get install -y libpng-dev git zlib1g-dev

RUN mkdir -p /usr/src/php/ext \
    && cd /usr/src/php/ext \
    && curl -fsSL https://github.com/igbinary/igbinary7/archive/master.tar.gz -o igbinary.tar.gz \
    && mkdir -p igbinary \
    && tar -xf igbinary.tar.gz -C igbinary --strip-components=1 \
    && rm igbinary.tar.gz \
    && docker-php-ext-install igbinary

RUN docker-php-ext-install gd \
    && docker-php-ext-install pcntl \
    && docker-php-ext-install mbstring \
    && docker-php-ext-install zip

WORKDIR /app

ENTRYPOINT []

CMD [ "/bin/bash" ]