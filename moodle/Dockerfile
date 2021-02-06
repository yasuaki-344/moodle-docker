FROM php:7-alpine
RUN apk --no-cache add \
    apache2 \
    graphviz aspell ghostscript clamav wget \
    mysql-client \
    php7-fpm \
    php7-opcache \
    php7-apache2 \
    php7-pecl-apcu \
    php7-mysqli \
    php7-pgsql \
    php7-json \
    php7-openssl \
    php7-curl \
    php7-zlib \
    php7-soap \
    php7-xml \
    php7-fileinfo \
    php7-phar \
    php7-intl \
    php7-dom \
    php7-xmlreader \
    php7-ctype \
    php7-session \
    php7-iconv \
    php7-xmlrpc \
    php7-zip \
    php7-simplexml \
    php7-mbstring \
    php7-gd \
    php7-tokenizer \
    phpldapadmin

RUN cd /tmp/ \
    && wget https://download.moodle.org/stable39/moodle-latest-39.tgz \
    && tar -zxvf moodle-latest-39.tgz \
    && rm /tmp/moodle-latest-39.tgz \
    && mv /tmp/moodle /var/www/localhost/htdocs \
    && chown apache:apache -R /var/www/localhost/htdocs -R \
    && chmod 0755 /var/www/localhost/htdocs -R \
    && mkdir /var/www/localhost/moodledata \
    && chown apache /var/www/localhost/moodledata -R \
    && chmod 0770 /var/www/localhost/moodledata -R
EXPOSE 80
VOLUME [ "/var/www/localhost/moodledata" ]
CMD ["httpd", "-D", "FOREGROUND"]
