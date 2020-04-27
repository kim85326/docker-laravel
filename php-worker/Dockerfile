ARG VERSION="7.3"

FROM php:${VERSION}-fpm

# Image Preinstalled extension: ctype json mbstring PDO tokenizer xml
# Laravel required extension: bcmath ctype json mbstring PDO tokenizer xml
RUN apt-get update \
    && apt-get install -y libpng-dev \ 
    && docker-php-ext-install gd bcmath pdo_mysql opcache

RUN apt-get install -y supervisor

RUN apt-get clean

COPY supervisord.conf /etc/supervisord.conf

WORKDIR /etc/supervisord.d/

CMD ["/usr/bin/supervisord", "-c", "/etc/supervisord.conf"]
