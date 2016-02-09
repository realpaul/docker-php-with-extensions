FROM php:5.6.18-cli

RUN set -ex \
	&& apt-get update \
	&& apt-get install -y php5-mysql \
	&& docker-php-ext-install mysql \
	&& docker-php-ext-install mysqli

CMD ["php", "-a"]