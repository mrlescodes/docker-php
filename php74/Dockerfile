FROM php:7.4-fpm

# Install dependencies
RUN apt-get update && apt-get install -y --no-install-recommends automake apt-utils git openssh-client rsync zip

# PHP Modules
ADD https://github.com/mlocati/docker-php-extension-installer/releases/latest/download/install-php-extensions /usr/local/bin/
RUN chmod +x /usr/local/bin/install-php-extensions && sync
RUN install-php-extensions zip

# Install nodejs
RUN curl -sL https://deb.nodesource.com/setup_14.x | bash - && \
    apt-get install -y nodejs && \
    npm install -g yarn

# Composer
RUN \
    curl https://getcomposer.org/composer-1.phar --output composer-1.phar && \
    curl https://getcomposer.org/composer-2.phar --output composer-2.phar && \
    mv composer-1.phar /usr/local/bin/composer && \
    mv composer-2.phar /usr/local/bin/composer-2 && \
    chmod +x /usr/local/bin/composer-2 && \
    chmod +x /usr/local/bin/composer
    