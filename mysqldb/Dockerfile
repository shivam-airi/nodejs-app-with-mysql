FROM mysql
ENV MYSQL_ROOT_PASSWORD=password@12345
COPY ./testdump.sql /docker-entrypoint-initdb.d/
VOLUME [ "/mysqldb/node_modules" ]
EXPOSE 3306
