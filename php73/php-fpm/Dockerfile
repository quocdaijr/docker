FROM phpdockerio/php73-fpm:latest

MAINTAINER NguyenQuocDai <quocdaijr@gmail.com>

COPY ./conf.d/overrides.conf /etc/php/7.3/fpm/pool.d/z-overrides.conf

RUN apt-get update \
    && apt-get -y --no-install-recommends install libmcrypt-dev mysql-client php7.3-redis php7.3-amqp php7.3-intl  \
    php7.3-mysql php7.3-pgsql php7.3-redis php7.3-bcmath php7.3-gd php7.3-igbinary php7.3-imagick php7.3-intl  \
    php7.3-mongodb php7.3-xmlrpc php7.3-xsl php7.3-yaml php7.3-memcached\
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /usr/share/doc/*

RUN apt-get update \
    && apt-get -y install git net-tools vim iputils-ping\
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /usr/share/doc/* 

RUN apt-get update \
    && apt-get -y install supervisor \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /usr/share/doc/* \
    && service supervisor start \
    && supervisorctl reload

RUN cp /usr/share/zoneinfo/Asia/Ho_Chi_Minh /etc/localtime

CMD ["/usr/sbin/php-fpm7.3", "-O" ]

EXPOSE 9000