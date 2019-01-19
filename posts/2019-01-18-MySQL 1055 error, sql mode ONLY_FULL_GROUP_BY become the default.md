## MySQL 1055 error, sql mode ONLY_FULL_GROUP_BY become the default

We encountered a sql_mode problem when our test environment migrated.
Our O&M team upgraded version of MySQL to 5.7.24.
Many modes keep up with OracleDB since MySQL was acquired by Oracle and the problem we encountered also caused by this.
With MySQL 5.7 ONLY_FULL_GROUP_BY will become the default.

[check this blog on mysqlserverteam](http://mysqlserverteam.com/mysql-5-7-only_full_group_by-improved-recognizing-functional-dependencies-enabled-by-default/)

[document description of MySQL](https://dev.mysql.com/doc/refman/5.7/en/group-by-handling.html)

Try this on your MySQL command line:
```
mysql> SELECT @@SQL_MODE, @@GLOBAL.SQL_MODE;
```
and the result similarly like:
```
ONLY_FULL_GROUP_BY,STRICT_TRANS_TABLES,NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_AUTO_CREATE_USER,NO_ENGINE_SUBSTITUTION
```
temporary solution, set sql_mode with no ONLY_FULL_GROUP_BY：
```
set @@GLOBAL.sql_mode=STRICT_TRANS_TABLES,NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_AUTO_CREATE_USER,NO_ENGINE_SUBSTITUTION;
```


