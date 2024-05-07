# Base image
FROM    debian:bullseye

RUN        apt update && apt install --no-install-recommends --no-install-suggests -y \
    php7.4-fpm -y \
    php7.4-mysql -y \
    wget

RUN wget --no-check-certificate --progress=dot:giga https://raw.githubusercontent.com/wp-cli/builds/gh-pages/phar/wp-cli.phar -O /tmp/wp-cli.phar && \
    mv /tmp/wp-cli.phar /usr/local/bin/wp && \
    chmod +x /usr/local/bin/wp

COPY ./conf/www.conf /etc/php/7.4/fpm/pool.d/
COPY ./tools/setup.sh /usr/local/bin

# Script execution
ENTRYPOINT ["sh", "/usr/local/bin/setup.sh"]
