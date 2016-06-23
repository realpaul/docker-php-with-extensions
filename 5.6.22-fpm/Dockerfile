FROM php:5.6.22-fpm-alpine

RUN set -ex \
  apk add --update bash build-base wget curl m4 autoconf libtool imagemagick imagemagick-dev \
  && printf "\n" | pecl install timezonedb imagick \
  && docker-php-ext-enable timezonedb imagick \
  && docker-php-ext-install bcmath bz2 calendar ctype curl dba dom enchant exif fileinfo filter ftp gd gettext gmp hash iconv imap interbase intl json ldap mbstring mcrypt mysql mysqli oci8 odbc opcache pcntl pdo pdo_dblib pdo_firebird pdo_mysql pdo_oci pdo_odbc pdo_pgsql pdo_sqlite pgsql phar posix pspell readline recode reflection session shmop simplexml snmp soap sockets spl standard sysvmsg sysvsem sysvshm tidy tokenizer wddx xml xmlreader xmlrpc xmlwriter xsl zip openssl \
  && cd /tmp \
  && wget -O /tmp/newrelic.tar.gz http://download.newrelic.com/php_agent/archive/newrelic-php5-6.4.0.163-linux.tar.gz \
  && mkdir /opt \
  && tar xfz /tmp/newrelic.tar.gz -C /opt \
  && mv /opt/newrelic-php5-6.4.0.163-linux /opt/newrelic-install \
  && rm -rf /tmp/newrelic*

EXPOSE 9000
CMD ["php-fpm"]