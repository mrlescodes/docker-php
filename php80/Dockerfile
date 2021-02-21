FROM php:8.0-fpm

# Install dependencies
RUN apt-get update && apt-get install -y --no-install-recommends automake apt-utils git openssh-client rsync zip unzip

# PHP Modules
ADD https://github.com/mlocati/docker-php-extension-installer/releases/latest/download/install-php-extensions /usr/local/bin/
RUN chmod +x /usr/local/bin/install-php-extensions && sync
RUN install-php-extensions zip

# Install Composer
RUN curl https://getcomposer.org/composer-1.phar --output composer-1.phar
RUN mv composer-1.phar /usr/local/bin/composer
RUN chmod +x /usr/local/bin/composer
    
# Install nodejs
RUN curl -sL https://deb.nodesource.com/setup_14.x | bash -
RUN apt-get install -y nodejs
RUN npm install -g yarn
