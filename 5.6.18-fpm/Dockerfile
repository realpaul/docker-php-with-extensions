FROM php:5.6.18-fpm

RUN set -ex \
	&& apt-get update \
	&& apt-get install -y php5-mysql \
	&& docker-php-ext-install mysql \
	&& docker-php-ext-install mysqli

EXPOSE 9000
CMD ["php-fpm"]