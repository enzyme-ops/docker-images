FROM alpine:3.7

RUN \
    mkdir /var/run/nginx/; \
    mkdir /var/run/php-fpm/; \
    apk update; \
    apk add \
        php7 \
        php7-openssl \
        php7-pdo \
        php7-cli \
        php7-mbstring \
        php7-tokenizer \
        php7-xml \
        php7-ctype \
        php7-json \
        php7-fpm \
        php7-pdo_mysql \
        php7-session \
        nginx; \
    adduser -D -g 'www' www; \
    chown -R www:www /var/lib/php7; \
    chown -R www:www /var/lib/nginx;

COPY ./nginx/nginx.conf /etc/nginx/nginx.conf
COPY ./nginx/default.conf /etc/nginx/conf.d/default.conf
COPY ./fpm/z-www.conf /etc/php7/php-fpm.d/z-www.conf

COPY entrypoint.sh /
RUN chmod +x /entrypoint.sh
ENTRYPOINT ["/entrypoint.sh"]

EXPOSE 80
