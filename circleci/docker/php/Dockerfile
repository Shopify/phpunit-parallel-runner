# code climate coverage reports needs xdebug and the report submitter needs git to work
FROM php:5.6

RUN yes | pecl install -f xdebug \
    && echo "zend_extension=$(find /usr/local/lib/php/extensions/ -name xdebug.so)" > /usr/local/etc/php/conf.d/xdebug.ini \
    && echo "xdebug.remote_enable=on" >> /usr/local/etc/php/conf.d/xdebug.ini \
    && echo "xdebug.remote_autostart=off" >> /usr/local/etc/php/conf.d/xdebug.ini

RUN apt-get update && \
    apt-get install git -y

COPY php.ini /usr/local/etc/php/php.ini

CMD ["php"]