FROM php:5.6.18-cli

RUN set -ex \
	&& apt-get update \
	&& apt-get install -y php5-mysql \
	&& apt-get install -y libapache2-mod-php5 \
	&& docker-php-ext-install mysql \
	&& docker-php-ext-install mysqli \
	&& docker-php-ext-install pdo pdo_mysql \
	&& docker-php-ext-install mbstring json session fileinfo exif gettext sockets

CMD ["php", "-a"]