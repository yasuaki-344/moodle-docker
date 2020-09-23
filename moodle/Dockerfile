FROM alpine:latest
ENV TZ=Asia/Tokyo
# 必要なライブラリ一覧のインストール
RUN apk --no-cache add \
    apache2 \
    graphviz aspell ghostscript clamav wget \
    mysql-client \
    php7 \
    php7-apache2 \
    php7-iconv \
    php7-fileinfo \
    phpldapadmin \
    php7-mysqli \
    php7-session \
    php7-json \
    php7-xml \
    php7-curl \
    php7-zip \
    php7-zlib \
    php7-gd \
    php7-dom \
    php7-xmlreader \
    php7-mbstring \
    php7-openssl \
    php7-xmlrpc \
    php7-soap \
    php7-intl \
    php7-opcache \
    php7-tokenizer \
    php7-simplexml \
    php7-ctype
# moodle環境の構築
RUN cd /tmp/ && \
    wget https://download.moodle.org/stable39/moodle-latest-39.tgz && \
    tar -zxvf moodle-latest-39.tgz && \
    rm /tmp/moodle-latest-39.tgz && \
    mv /tmp/moodle /var/www/localhost/htdocs && \
    chown apache:apache -R /var/www/localhost/htdocs -R && \
    chmod 0755 /var/www/localhost/htdocs -R && \
    mkdir /var/www/localhost/moodledata && \
    chown apache /var/www/localhost/moodledata -R && \
    chmod 0770 /var/www/localhost/moodledata -R

EXPOSE 80
VOLUME [ "/var/www/localhost/moodledata" ]
CMD ["httpd", "-D", "FOREGROUND"]
