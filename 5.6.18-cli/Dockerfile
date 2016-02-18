FROM php:5.6.18-cli

RUN set -ex \
	&& apt-get update \
	&& apt-get install -y php5-mysql \
	&& apt-get install -y libapache2-mod-php5 \
	&& docker-php-ext-install mysql \
	&& docker-php-ext-install mysqli \
	&& docker-php-ext-install bcmath bz2 calendar ctype date dba dom ereg exif fileinfo filter ftp gettext hash iconv json libxml mbstring openssl pcre posix session shmop soap sockets standard sysvmsg sysvsem sysvshm tokenizer wddx xml xmlreader xmlwriter zip zlib

CMD ["php", "-a"]