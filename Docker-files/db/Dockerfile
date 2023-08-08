FROM mysql:8.0.33
LABEL "Project"="vProfile"
LABEL "Author"="abhishekm89"

ENV MYSQL_ROOT_PASSWORD="admin123"
ENV MYSQL_DATABASE="accounts"

ADD db_backup.sql /docker-entrypoint-initdb.d
EXPOSE 3306