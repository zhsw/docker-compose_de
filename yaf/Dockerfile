FROM php:7.4-fpm-alpine

COPY yaf-3.3.2.tgz /var/www/html/yaf-3.3.2.tgz

RUN sed -i 's/dl-cdn.alpinelinux.org/mirrors.ustc.edu.cn/g' /etc/apk/repositories && \
#    sed -i 's/nameserver/#nameserver/g' /etc/resolv.conf && \
    echo 'nameserver 114.114.114.114' > /etc/resolv.conf && \
    apk add autoconf gcc libc-dev make && pecl install yaf-3.3.2.tgz && \
    echo "extension=yaf.so" > /usr/local/etc/php/conf.d/pecl-ext.ini && \
    rm yaf-3.3.2.tgz