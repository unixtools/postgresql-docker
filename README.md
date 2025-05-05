# postgresql
postgresql tools and scripts for use with docker based deployment

Requires: /local/postgres-db-backups to be mounted as same path within container named postgres




root@vm-appname:/local/postgres# docker exec -it postgres psql -U postgres
psql (17.4 (Debian 17.4-1.pgdg120+2))
Type "help" for help.

postgres=# create database appname;
CREATE DATABASE
postgres=# create user appname with encrypted password '---snip---';
CREATE ROLE
postgres=# grant all privileges on database appname to appname;
GRANT
postgres=# alter database appname owner to appname;
ALTER DATABASE
postgres=# \connect appname
You are now connected to database "appname" as user "postgres".
appname=# grant all on schema public to appname;
GRANT



#
# Run the above for user 'root' db 'root' - but don't set the password
# This will silence the container warnings about root role missing - may be a better way for this though
#
