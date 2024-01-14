FROM php:8.2-fpm
# work directory
WORKDIR /var/www/laravel
# add extensions
RUN docker-php-ext-install pdo pdo_mysql

# xdebug
#RUN pecl install xdebug \
#    && docker-php-ext-enable xdebug