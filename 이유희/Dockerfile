# cat Dockerfile
FROM --platform=linux/amd64 mysql:latest

RUN chown -R mysql:root /var/lib/mysql/

ARG MYSQL_DATABASE='my_sql_study'
ARG MYSQL_USER='guetnLEE'
ARG MYSQL_PASSWORD='123'
ARG MYSQL_ROOT_PASSWORD='123'

ENV MYSQL_DATABASE=$MYSQL_DATABASE
ENV MYSQL_USER=$MYSQL_USER
ENV MYSQL_PASSWORD=$MYSQL_PASSWORD
ENV MYSQL_ROOT_PASSWORD=$MYSQL_ROOT_PASSWORD

ADD data.sql /etc/mysql/data.sql

#VOLUME . /var/lib/mysql

RUN sed -i 's/MYSQL_DATABASE/'$MYSQL_DATABASE'/g' /etc/mysql/data.sql
RUN cp /etc/mysql/data.sql /docker-entrypoint-initdb.d

EXPOSE 3306