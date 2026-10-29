FROM php:8.5.12-fpm-alpine

# Install Composer.
RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
RUN php composer-setup.php
RUN php -r "unlink('composer-setup.php');"
RUN mv composer.phar /usr/local/bin/composer
RUN chmod +x /usr/local/bin/composer

# Install Composer packages.
COPY composer.json .
COPY composer.lock .
RUN composer install --no-interaction --no-plugins --no-scripts --no-dev

CMD ["php-fpm"]
