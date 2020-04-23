FROM php:fpm

# Image Preinstalled extension: ctype json mbstring PDO tokenizer xml
# Laravel required extension: bcmath ctype json mbstring PDO tokenizer xml
RUN apt-get update \
    && apt-get install -y libpng-dev \ 
    && docker-php-ext-install gd bcmath pdo_mysql opcache

RUN apt-get clean

CMD ["php-fpm"]
