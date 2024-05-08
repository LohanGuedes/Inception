# Base image
FROM    debian:bullseye

RUN        apt update && \
    apt install -y --no-install-recommends --no-install-suggests \
    mariadb-server

COPY    conf/50-server.cnf /etc/mysql/mariadb.conf.d/

COPY    tools/create-database-script.sh /bin/
RUN        chmod +x /bin/create-database-script.sh

CMD        ["create-database-script.sh"]

