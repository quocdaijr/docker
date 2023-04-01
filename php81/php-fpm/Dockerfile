FROM phpdockerio/php:8.1-fpm
MAINTAINER NguyenQuocDai <quocdaijr@gmail.com>

RUN apt-get update \
    && apt-get -y --no-install-recommends install libmcrypt-dev mysql-client php8.1-redis php8.1-amqp php8.1-intl \
    php8.1-mysql php8.1-pgsql php8.1-bcmath php8.1-gd php8.1-igbinary php8.1-imagick php8.1-intl php8.1-mongodb \
    php8.1-memcached php8.1-xmlrpc php8.1-xsl php8.1-yaml \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /usr/share/doc/*

RUN apt-get update \
    && apt-get -y --no-install-recommends install npm \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /usr/share/doc/*

RUN apt-get update \
    && npm install -g n && n stable \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /usr/share/doc/*

RUN apt-get update \
    && apt-get -y install git net-tools vim iputils-ping telnet\
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /usr/share/doc/*

RUN apt-get update \
    && apt-get -y install supervisor \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /usr/share/doc/*

RUN cp /usr/share/zoneinfo/Asia/Ho_Chi_Minh /etc/localtime

CMD ["/usr/sbin/php-fpm8.1", "-O"]

EXPOSE 9000