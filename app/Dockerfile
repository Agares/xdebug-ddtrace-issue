FROM php:7.4.3-fpm

RUN curl -L -o datadog-php-tracer_0.42.0_amd64.deb https://github.com/DataDog/dd-trace-php/releases/download/0.42.0/datadog-php-tracer_0.42.0_amd64.deb \
	&& dpkg -i datadog-php-tracer_0.42.0_amd64.deb \
	&& rm datadog-php-tracer_0.42.0_amd64.deb
	
RUN pecl install xdebug-2.9.1
RUN echo "zend_extension=xdebug" > /usr/local/etc/php/conf.d/00-xdebug.ini
RUN echo "xdebug.remote_enable=1" >> /usr/local/etc/php/conf.d/00-xdebug.ini

RUN mkdir -p /var/www
RUN echo "<?php phpinfo();" > /var/www/index.php