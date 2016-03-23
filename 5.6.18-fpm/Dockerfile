FROM php:5.6.18-fpm

RUN set -ex \
	&& apt-get update \
	&& apt-get install -y wget \
	&& wget -O /tmp/temp.gpg https://download.newrelic.com/548C16BF.gpg \
	&& apt-key add /tmp/temp.gpg \
	&& rm -rf /tmp/temp.gpg \
	&& echo "deb http://apt.newrelic.com/debian/ newrelic non-free" > /etc/apt/sources.list.d/newrelic.list \
	&& apt-get update \
	&& apt-get install -y newrelic-php5 \
	&& echo newrelic-install install \
	&& apt-get install -y libmcrypt-dev php5-mcrypt \
	&& apt-get install -y libcurl4-openssl-dev libssl-dev \
	&& apt-get install -y php5-mysql \
	&& apt-get install -y php5-gd libfreetype6-dev libjpeg62-turbo-dev libpng12-dev \
	&& apt-get install -y libapache2-mod-php5 \
	&& docker-php-ext-install mcrypt \
	&& docker-php-ext-install openssl \
	&& docker-php-ext-install mysql \
	&& docker-php-ext-install mysqli \
	&& docker-php-ext-install pdo pdo_mysql \
  && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
  && docker-php-ext-install -j$(nproc) gd \
	&& docker-php-ext-install mbstring json session fileinfo exif gettext sockets zip

EXPOSE 9000
CMD ["php-fpm"]