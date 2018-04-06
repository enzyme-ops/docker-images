FROM alpine:3.7

MAINTAINER Tristan Strathearn <tristan@pixls.com.au>

# CircleCI required dependencies.
RUN \
    apk update; \
    apk add \
        git \
        openssh-client \
        ca-certificates;

# Image dependencies.
RUN \
    apk add \
        php7 \
        php7-dom \
        php7-json \
        php7-xdebug \
        php7-phar \
        php7-openssl \
        php7-pdo \
        php7-pdo_mysql \
        php7-pdo_sqlite \
        php7-pdo_pgsql \
        php7-mbstring \
        php7-xml \
        php7-ctype \
        php7-session \
        php7-tokenizer; \
    rm -rf /var/cache/apk/*; \
    wget https://phar.phpunit.de/phpunit-6.5.phar; \
    chmod +x phpunit-6.5.phar; \
    mv phpunit-6.5.phar /usr/local/bin/phpunit;
