# operations-sql
operations
Setting environment for using XAMPP for Windows.
pavan@DESKTOP-AP8KEL0 c:\xampp
# mysql.exe -u root
Welcome to the MariaDB monitor.  Commands end with ; or \g.
Your MariaDB connection id is 9
Server version: 10.4.28-MariaDB mariadb.org binary distribution

Copyright (c) 2000, 2018, Oracle, MariaDB Corporation Ab and others.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

MariaDB [(none)]> show databases;
+--------------------+
| Database           |
+--------------------+
| fish               |
| information_schema |
| mysql              |
| nari               |
| performance_schema |
| phpmyadmin         |
| praveen            |
| test               |
+--------------------+
8 rows in set (0.002 sec)

MariaDB [(none)]> use fish;
Database changed
MariaDB [fish]> desc employee;
+-------+------------+------+-----+---------+-------+
| Field | Type       | Null | Key | Default | Extra |
+-------+------------+------+-----+---------+-------+
| eid   | int(11)    | YES  |     | NULL    |       |
| name  | varchar(9) | YES  |     | NULL    |       |
| salry | int(11)    | YES  |     | NULL    |       |
+-------+------------+------+-----+---------+-------+
3 rows in set (0.017 sec)

MariaDB [fish]>  insert into employee values(01,'praveen',10000),(02,'nari',12000),(03,'mohan',11000),(04,'pavan',20000),(05,'rakesh',15000);
Query OK, 5 rows affected (0.056 sec)
Records: 5  Duplicates: 0  Warnings: 0

MariaDB [fish]> select * from employee;
+------+---------+-------+
| eid  | name    | salry |
+------+---------+-------+
|    1 | praveen | 10000 |
|    2 | nari    | 12000 |
|    3 | pavan   | 11000 |
|    4 | mohan   | 20000 |
|    5 | rakesh  | 14000 |
|    1 | praveen | 10000 |
|    2 | nari    | 12000 |
|    3 | mohan   | 11000 |
|    4 | pavan   | 20000 |
|    5 | rakesh  | 15000 |
+------+---------+-------+
10 rows in set (0.000 sec)

MariaDB [fish]> select * from employee where salry <14000;
+------+---------+-------+
| eid  | name    | salry |
+------+---------+-------+
|    1 | praveen | 10000 |
|    2 | nari    | 12000 |
|    3 | pavan   | 11000 |
|    1 | praveen | 10000 |
|    2 | nari    | 12000 |
|    3 | mohan   | 11000 |
+------+---------+-------+
6 rows in set (0.001 sec)

MariaDB [fish]> select * from employee where salry >12000;
+------+--------+-------+
| eid  | name   | salry |
+------+--------+-------+
|    4 | mohan  | 20000 |
|    5 | rakesh | 14000 |
|    4 | pavan  | 20000 |
|    5 | rakesh | 15000 |
+------+--------+-------+
4 rows in set (0.001 sec)

MariaDB [fish]> select * from employee where salry >=12000;
+------+--------+-------+
| eid  | name   | salry |
+------+--------+-------+
|    2 | nari   | 12000 |
|    4 | mohan  | 20000 |
|    5 | rakesh | 14000 |
|    2 | nari   | 12000 |
|    4 | pavan  | 20000 |
|    5 | rakesh | 15000 |
+------+--------+-------+
6 rows in set (0.001 sec)

MariaDB [fish]> select * from employee where salry <=15000;
+------+---------+-------+
| eid  | name    | salry |
+------+---------+-------+
|    1 | praveen | 10000 |
|    2 | nari    | 12000 |
|    3 | pavan   | 11000 |
|    5 | rakesh  | 14000 |
|    1 | praveen | 10000 |
|    2 | nari    | 12000 |
|    3 | mohan   | 11000 |
|    5 | rakesh  | 15000 |
+------+---------+-------+
8 rows in set (0.001 sec)

MariaDB [fish]> select * from employee where salry between 12000 and 15000;
+------+--------+-------+
| eid  | name   | salry |
+------+--------+-------+
|    2 | nari   | 12000 |
|    5 | rakesh | 14000 |
|    2 | nari   | 12000 |
|    5 | rakesh | 15000 |
+------+--------+-------+
4 rows in set (0.001 sec)

MariaDB [fish]> select * from employee where eid <> 2;
+------+---------+-------+
| eid  | name    | salry |
+------+---------+-------+
|    1 | praveen | 10000 |
|    3 | pavan   | 11000 |
|    4 | mohan   | 20000 |
|    5 | rakesh  | 14000 |
|    1 | praveen | 10000 |
|    3 | mohan   | 11000 |
|    4 | pavan   | 20000 |
|    5 | rakesh  | 15000 |
+------+---------+-------+
8 rows in set (0.001 sec)
