FROM arm32v7/debian:buster-slim

RUN apt-get update && apt-get install -y \ 
    nginx \
    cron \
    certbot \
    python-certbot-nginx

COPY ./renewcerts /etc/cron.d/
COPY ./entrypoint.sh /

ENTRYPOINT ["/entrypoint.sh"]

