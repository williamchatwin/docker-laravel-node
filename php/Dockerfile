FROM php:7-fpm

# replace shell with bash so we can source files
RUN rm /bin/sh && ln -s /bin/bash /bin/sh

# Install PDO php extensions for Laravel
RUN docker-php-ext-install pdo pdo_mysql

# Set the directory this container work in
WORKDIR /var/www/app

# Get dependencies for composer
RUN apt-get update \
    && apt-get install -y --no-install-recommends git zip \
    && apt install zip unzip -y

# Install composer executable
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/bin/ --filename=composer

# nvm environment variables
ENV NVM_DIR /usr/local/nvm
ENV NODE_VERSION 8.11.3

# Install nvm
# https://github.com/creationix/nvm#install-script
RUN curl --silent -o- https://raw.githubusercontent.com/creationix/nvm/v0.31.2/install.sh | bash

# Install node and npm
RUN source $NVM_DIR/nvm.sh \
    && nvm install $NODE_VERSION \
    && nvm alias default $NODE_VERSION \
    && nvm use default

# add node and npm to path so the commands are available
ENV NODE_PATH $NVM_DIR/v$NODE_VERSION/lib/node_modules
ENV PATH $NVM_DIR/versions/node/v$NODE_VERSION/bin:$PATH

EXPOSE 80
EXPOSE 8000
