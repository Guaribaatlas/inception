FROM debian:buster

RUN apt-get update &&\
    apt-get upgrade -y &&\
    apt-get install -y mariadb-server &&\
    apt-get install -y vim


EXPOSE 3306

COPY data/my.cnf /etc/mysql/
COPY data/setup.sh .
COPY data/wp-db.sql .

RUN chmod +x setup.sh

CMD /setup.sh
