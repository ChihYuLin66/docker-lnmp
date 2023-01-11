FROM phpdockerio/php56-fpm
WORKDIR "/var/www/html"

# FROM php:5.6-cli

# ADD https://github.com/mlocati/docker-php-extension-installer/releases/latest/download/install-php-extensions /usr/local/bin/

# RUN chmod +x /usr/local/bin/install-php-extensions && \
#     install-php-extensions gd xdebug

RUN apt-get update && apt-get -y upgrade
RUN apt-get install -y \
    telnet \
    net-tools \
    iputils-ping \
    ntp \ 
    unzip
    
RUN apt install -y wget software-properties-common
RUN echo "Asia/Taipei" > /etc/timezone
RUN rm -f /etc/localtime
RUN ln -fs /usr/share/zoneinfo/Asia/Taipei /etc/localtime

RUN add-apt-repository ppa:ondrej/php

# RUN curl -sSLf \
#         -o /usr/local/bin/install-php-extensions \
#         https://github.com/mlocati/docker-php-extension-installer/releases/latest/download/install-php-extensions && \
#     chmod +x /usr/local/bin/install-php-extensions && \
#     install-php-extensions gd xdebug

# COPY --from=mlocati/php-extension-installer /usr/bin/install-php-extensions /usr/local/bin/

# RUN install-php-extensions gd xdebug

# RUN apt-get update && apt-get install -y php5.6-common 
# RUN apt-get update && apt-get install -y php5.6-cli 
# RUN apt-get update && apt-get install -y php5.6-gd 
# RUN apt-get update && apt-get install -y php5.6-mysql 
# RUN apt-get update && apt-get install -y php5.6-imap 
# RUN apt-get update && apt-get install -y php5.6-curl 
# RUN apt-get update && apt-get install -y php5.6-intl 
# RUN apt-get update && apt-get install -y php5.6-pspell 
# RUN apt-get update && apt-get install -y php5.6-recode 
# RUN apt-get update && apt-get install -y php5.6-sqlite3 
# RUN apt-get update && apt-get install -y php5.6-tidy 
# RUN apt-get update && apt-get install -y php5.6-xmlrpc 
# RUN apt-get update && apt-get install -y php5.6-xsl 
# RUN apt-get update && apt-get install -y php5.6-zip 
# RUN apt-get update && apt-get install -y php5.6-mbstring 
# RUN apt-get update && apt-get install -y php5.6-soap 
# RUN apt-get update && apt-get install -y php5.6-opcache 
# RUN apt-get update && apt-get install -y libicu65 
# RUN apt-get update && apt-get install -y php5.6-json 
# RUN apt-get update && apt-get install -y php5.6-readline 
# RUN apt-get update && apt-get install -y php5.6-xml

RUN apt-get install -y php5-mysql
RUN apt-get install -y php5-mysqlnd

## mysql 連線時只要填 mysql的container name