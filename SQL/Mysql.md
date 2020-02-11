# MySQL

``` text
mysql -u username -p
enter password
```

``` sql
create database blog_development;
grant all on blog_development.* to username@localhost identified by ‘password’;
```

``` text
cd into /var/www/html/appname/
rake db:migrate
```

``` sql
show databases
use blog_development
show tables from blog_development
```

``` sql
Create new user
CREATE USER ‘newuser’@‘localhost’ IDENTIFIED BY ‘password’;
GRANT ALL PRIVILEGES ON * . * TO ‘newuser’@‘localhost’;
FLUSH PRIVILEGES;
```

``` sql
Remove user
DROP USER ‘demo’@‘localhost’;
```

``` sql
Revoke user permissions
REVOKE [type of permission] ON [database name].[table name] FROM ‘[username]’@‘localhost’;
```

``` sql
ALTER TABLE contacts ADD email VARCHAR(60);
```

``` text
$ mysqldump -u root -p TUTORIALS tutorials_tbl > dump.sql
```

Permission Types

`ALL PRIVILEGES`
allow a MySQL user all access to a designated database (or if no database is selected, across the system)

`CREATE`
allows them to create new tables or databases

`DROP`
allows them to them to delete tables or databases

`DELETE`
allows them to delete rows from tables

`INSERT`
allows them to insert rows into tables

`SELECT`
allows them to use the Select command to read through databases

`UPDATE`
allow them to update table rows

`GRANT OPTION`
allows them to grant or remove other users’ privileges
