FROM php:5.6.18-fpm

RUN set -ex \
	&& apt-get update \
	&& apt-get install -y php5-mysql \
	&& apt-get install -y libapache2-mod-php5 \
	&& docker-php-ext-install mysql \
	&& docker-php-ext-install mysqli \
	&& docker-php-ext-install mbstring json session fileinfo exif gettext

EXPOSE 9000
CMD ["php-fpm"]