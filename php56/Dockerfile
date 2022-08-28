FROM php:5.6-apache
WORKDIR "/var/www/html"

####################################
# Update and install network tools, set system default timezone
####################################
# RUN apt-get update && apt-get -y upgrade
# RUN apt-get install -y \
#     telnet \
#     net-tools \
#     iputils-ping \
#     ntp \ 
#     unzip
    
# RUN apt install -y wget software-properties-common
# RUN echo "Asia/Taipei" > /etc/timezone
# RUN rm -f /etc/localtime
# RUN ln -fs /usr/share/zoneinfo/Asia/Taipei /etc/localtime

# RUN add-apt-repository ppa:ondrej/php

# RUN apt-get update && apt-get install -y \
#         libbz2-dev \
#         libfreetype6-dev \
#         libgd-dev \
#         libjpeg62-turbo-dev \
#         libmcrypt-dev \
#         libpng-dev \
#         libxml2-dev \
#         zlib1g-dev \
#     && docker-php-ext-install iconv mbstring mcrypt soap sockets zip \
#     && docker-php-ext-configure gd --enable-gd-native-ttf --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
#     && docker-php-ext-install gd \
#     && docker-php-ext-configure mysql --with-mysql=mysqlnd \
#     && docker-php-ext-install mysql

# RUN apt-get update \
#     && apt-get install -y \ 
#     php5.6-common \
#     php5.6-mysql \
#     php5.6-xml \
#     php5.6-xmlrpc \
#     php5.6-curl \
#     php5.6-gd \
#     php5.6-imagick \
#     php5.6-cli \
#     php5.6-dev \
#     php5.6-imap \
#     php5.6-mbstring \
#     php5.6-opcache \
#     php5.6-soap \
#     php5.6-zip 

####################################
# Install composer tool 
####################################
RUN curl -sS https://getcomposer.org/installer | php && mv composer.phar /usr/local/bin/composer
RUN apt-get update && apt install unzip && apt-get clean && rm -rf /var/lib/apt/lists/*

# Replace shell with bash so we can source files
RUN rm /bin/sh && ln -s /bin/bash /bin/sh

# Set debconf to run non-interactively
RUN echo 'debconf debconf/frontend select Noninteractive' | debconf-set-selections


####################################
# Install Nodejs, npm, nvm
####################################
RUN curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.3/install.sh | bash 
RUN export NVM_DIR="$([ -z "${XDG_CONFIG_HOME-}" ] && printf %s "${HOME}/.nvm" || printf %s "${XDG_CONFIG_HOME}/nvm")" && \
     [ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh" && \
     nvm install 12.22.1 && \
     nvm use 12.22.1

####################################
# Create normal group and user 
####################################
ARG NORMAL_USER 
ENV NORMAL_USER=${NORMAL_USER}
ARG NORMAL_GROUP 
ENV NORMAL_GROUP=${NORMAL_GROUP}

RUN groupadd -g 1000 ${NORMAL_GROUP}
RUN useradd -d /home/${NORMAL_USER} -g ${NORMAL_GROUP} -s /bin/bash ${NORMAL_USER}
