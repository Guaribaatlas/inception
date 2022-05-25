FROM debian:buster
RUN apt-get update && \
    apt-get upgrade && \
    apt-get install -y nginx &&\
    apt-get install-openssl

COPY data/nginx.conf /etc/nginx/sites-enabled
COPY data/my_wp.conf /etc/nginx/

RUN openssl req -x509 -nodes -days 30 -subj "/C=BE/ST=Belgium/L=Brussels/O=42Network/OU=s19/CN=jehaenec" -newkey rsa:4096 -keyout /etc/ssl/nginx-selfsigned.key -out /etc/ssl/nginx-selfsigned.crt;

CMD nginx -g "daemeon-off;"