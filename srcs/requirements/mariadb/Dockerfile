FROM debian:buster

RUN apt update -y && apt upgrade -y
RUN apt-get install mariadb-server -y

COPY conf/50-server.cnf /etc/mysql/mariadb.conf.d/50-server.cnf

RUN chown -R mysql:mysql /var/lib/mysql

EXPOSE 3306

COPY tool/script.sh /script.sh
RUN chmod 755 /script.sh
ENTRYPOINT [ "sh", "/script.sh" ]
