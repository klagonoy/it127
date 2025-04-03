FROM bitnami/php-fpm:8.1.9
WORKDIR "/application"

RUN apt-get update;

RUN apt-get -y --no-install-recommends install\
    php-zip zip unzip php8.1-mysql php-imagick php8.1-intl php8.1-soap php8.1-gd php8.1-ext-dom;\
    apt-get clean;\
    rm -rf /var/lib/apt/list/* /tmp/* /var/tmp/* /usr/share/doc/*
RUN apt-get -y install patch;

RUN mkdir /tmp/composer/ && \
    cd /tmp/composer && \
    curl -sS https://getcomposer.org/installer | php && \
    mv composer.phar /usr/local/bin/composer && \
    chmod a+x /usr/local/bin/composer && \
    cd / && \
    rm -rf /tmp/composer