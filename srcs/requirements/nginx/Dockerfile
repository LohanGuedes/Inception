# Base image
FROM alpine:3.17

RUN apk update && apk add --no-cache nginx openssl

COPY ./conf/nginx.conf /etc/nginx/
COPY ./tools/setup.sh /tmp/

RUN chmod +x tmp/setup.sh

RUN ./tmp/setup.sh

ENTRYPOINT ["nginx", "-g", "daemon off;"]
