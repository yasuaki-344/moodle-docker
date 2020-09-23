FROM mysql:latest

COPY initial.sql /docker-entrypoint-init.d/initial.sql
VOLUME [ "/data/lib/mysql" ]

EXPOSE 3306