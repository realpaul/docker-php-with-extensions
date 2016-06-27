FROM php:7.0.7-fpm-alpine

RUN set -ex \
  && apk add --update bash build-base wget curl m4 autoconf libtool imagemagick imagemagick-dev zlib zlib-dev libcurl libevent libidn \
  && printf "\n" | pecl install raphf propro \
  && docker-php-ext-enable raphf propro \
  && printf "\n" | pecl install redis timezonedb imagick pecl_http \
  && docker-php-ext-enable redis timezonedb imagick http \
  && docker-php-ext-install bcmath bz2 calendar ctype curl dba dom enchant exif fileinfo filter ftp gd gettext gmp hash iconv imap interbase intl json ldap mbstring mcrypt mysqli oci8 odbc opcache pcntl pdo pdo_dblib pdo_firebird pdo_mysql pdo_oci pdo_odbc pdo_pgsql pdo_sqlite pgsql phar posix pspell readline recode reflection session shmop simplexml snmp soap sockets spl standard sysvmsg sysvsem sysvshm tidy tokenizer wddx xml xmlreader xmlrpc xmlwriter xsl zip openssl \
  && cd /tmp \
  && wget -O /tmp/newrelic.tar.gz http://download.newrelic.com/php_agent/archive/6.4.0.163/newrelic-php5-6.4.0.163-linux.tar.gz \
  && mkdir /opt \
  && tar xfz /tmp/newrelic.tar.gz -C /opt \
  && mv /opt/newrelic-php5-6.4.0.163-linux /opt/newrelic-install \
  && rm -rf /tmp/newrelic*

EXPOSE 9000
CMD ["php-fpm"]