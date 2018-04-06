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
        curl \
        php7 \
        php7-cli \
        php7-json \
        php7-openssl \
        php7-curl \
        php7-pdo \
        php7-pdo_mysql \
        php7-pdo_sqlite \
        php7-pdo_pgsql \
        php7-mbstring \
        php7-xml \
        php7-ctype \
        php7-dom \
        php7-xmlwriter \
        php7-session \
        php7-phar \
        php7-tokenizer; \
    rm -rf /var/cache/apk/*; \
    curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer; \
    composer global require hirak/prestissimo;
