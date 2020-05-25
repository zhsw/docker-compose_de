FROM php:7.2-fpm
MAINTAINER 1297286680@qq.com
WORKDIR /var/www
COPY amqp-1.10.2.tgz amqp-1.10.2.tgz
COPY redis-5.2.2.tgz redis-5.2.2.tgz
COPY swoole-4.5.1.tgz swoole-4.5.1.tgz
RUN echo "deb https://mirrors.aliyun.com/debian  stable main contrib non-free" > /etc/apt/sources.list \
    && echo "deb https://mirrors.aliyun.com/debian  stable-updates main contrib non-free" >> /etc/apt/sources.list \
    && apt-get update && apt-get install -y autoconf librabbitmq-dev libgmp-dev \
    && printf "\n" | pecl install --offline redis-5.2.2.tgz \
    && printf "\n" | pecl install --offline amqp-1.10.2.tgz \
    && printf "\n" | pecl install --offline swoole-4.5.1.tgz \
    && echo "extension=redis.so" > /usr/local/etc/php/conf.d/pecl-ext.ini \
    && echo "extension=amqp.so" >> /usr/local/etc/php/conf.d/pecl-ext.ini \
    && echo "extension=swoole.so" >> /usr/local/etc/php/conf.d/pecl-ext.ini \
    && docker-php-ext-install bcmath pdo_mysql mysqli gmp \
    && rm redis-5.2.2.tgz amqp-1.10.2.tgz swoole-4.5.1.tgz

# && curl -o go-pear.php  https://pear.php.net/go-pear && php go-pear.php
# RUN docker-php-ext-install bcmath bz2 calendar dba enchant exif gd
# gettext gmp imap interbase intl ldap mysqli oci8 odbc opcache pcntl pdo_dblib
# pdo_firebird pdo_mysql pdo_oci pdo_odbc pdo_pgsql pgsql pspell recode
# shmop snmp soap sockets sysvmsg sysvsem sysvshm tidy
# wddx xmlrpc xsl zend_test zip\