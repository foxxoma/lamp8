FROM php:8.0.2-apache
RUN apt-get -y update --fix-missing
RUN apt-get upgrade -y

# Install useful tools
RUN apt-get -y install apt-utils nano wget

# Install important libraries
RUN apt-get -y install --fix-missing apt-utils build-essential git curl zip
# Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

#RUN docker-php-ext-enable opcache
RUN docker-php-ext-install pdo_mysql
#RUN docker-php-ext-install pdo_sqlite
RUN docker-php-ext-install mysqli
#RUN docker-php-ext-install tokenizer
#RUN docker-php-ext-install json
RUN docker-php-ext-install exif
#RUN docker-php-ext-install -j$(nproc) intl

RUN a2enmod rewrite
RUN service apache2 restart
