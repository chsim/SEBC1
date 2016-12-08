```sh
==========================================================================================================
MYSQL INSTALLATION
==========================================================================================================
```
sudo rpm -ivh mysql57-community-release-el7-9.noarch.rpm

sudo yum update
sudo yum install mysql-server
sudo systemctl start mysqld
```

```sh
==========================================================================================================
INSTALL MYSQL JDBC CONNECTOR FILE
==========================================================================================================
```
sudo yum install mysql-connector-java

sudo systemctl stop mysqld
sudo systemctl start mysqld
```

```sh
==========================================================================================================
SECURE MYSQL
==========================================================================================================
```
[centos@ip-172-31-5-139 ~]$ sudo grep 'temporary password' /var/log/mysqld.log
2016-12-05T14:09:50.155051Z 1 [Note] A temporary password is generated for root@localhost: x8P2cH-CBofi
ZAQ!zaq112


$ sudo /usr/bin/mysql_secure_installation
[...]
Enter current password for root (enter for none):
OK, successfully used password, moving on...
[...]
Set root password? [Y/n] y
New password:
Re-enter new password:
Remove anonymous users? [Y/n] Y
[...]
Disallow root login remotely? [Y/n] N
[...]
Remove test database and access to it [Y/n] Y
[...]
Reload privilege tables now? [Y/n] Y
All done!


[centos@ip-172-31-5-139 ~]$ sudo systemctl list-unit-files|grep -i mysql
mysqld.service                         enabled
mysqld@.service                        disabled
```

```sh
==========================================================================================================
MYSQL VERSION
==========================================================================================================
```
 [centos@ip-172-31-5-139 ~]$ mysql --version
mysql  Ver 14.14 Distrib 5.7.16, for Linux (x86_64) using  EditLine wrapper
```


```sh
==========================================================================================================
STARTUP MYSQL 
==========================================================================================================
```
sudo systemctl start mysqld


[centos@ip-172-31-5-139 ~]$ sudo mysql -u root -p
Enter password:
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 2316
Server version: 5.7.16 MySQL Community Server (GPL)

Copyright (c) 2000, 2016, Oracle and/or its affiliates. All rights reserved.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

mysql> select version()
    -> ;
+-----------+
| version() |
+-----------+
| 5.7.16    |
+-----------+
1 row in set (0.07 sec)
```


```sh
==========================================================================================================
CREATE DATABASES FOR CLOUDERA MANAGER
==========================================================================================================
```
create database amon DEFAULT CHARACTER SET utf8;
create database rman DEFAULT CHARACTER SET utf8;
create database metastore DEFAULT CHARACTER SET utf8;
create database sentry DEFAULT CHARACTER SET utf8;
create database nav DEFAULT CHARACTER SET utf8;
create database navms DEFAULT CHARACTER SET utf8;

grant all on amon.* TO 'amon'@'%' IDENTIFIED BY 'ZAQ!zaq112';
grant all on rman.* TO 'rman'@'%' IDENTIFIED BY 'ZAQ!zaq112';
grant all on metastore.* TO 'hive'@'%' IDENTIFIED BY 'ZAQ!zaq112';
grant all on sentry.* TO 'sentry'@'%' IDENTIFIED BY 'ZAQ!zaq112';
grant all on nav.* TO 'nav'@'%' IDENTIFIED BY 'ZAQ!zaq112';
grant all on navms.* TO 'navms'@'%' IDENTIFIED BY 'ZAQ!zaq112';
```


```sh
==========================================================================================================
LIST DATABASES
==========================================================================================================
```


mysql> show databases;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| amon               |
| metastore          |
| mysql              |
| nav                |
| navms              |
| performance_schema |
| rman               |
| sentry             |
| sys                |
+--------------------+
12 rows in set (0.16 sec)
```

```sh
==========================================================================================================
LIST GRANTS 
==========================================================================================================
```
mysql> show grants;
+---------------------------------------------------------------------+
| Grants for root@localhost                                           |
+---------------------------------------------------------------------+
| GRANT ALL PRIVILEGES ON *.* TO 'root'@'localhost' WITH GRANT OPTION |
| GRANT PROXY ON ''@'' TO 'root'@'localhost' WITH GRANT OPTION        |
+---------------------------------------------------------------------+
2 rows in set (0.00 sec)

mysql>


[centos@ip-172-31-5-139 ~]$ sudo mysql -u rman -p
Enter password:
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 2348
Server version: 5.7.16 MySQL Community Server (GPL)

Copyright (c) 2000, 2016, Oracle and/or its affiliates. All rights reserved.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

mysql> SELECT * FROM information_schema.user_privileges;
+----------------------------+---------------+-------------------------+--------------+
| GRANTEE                    | TABLE_CATALOG | PRIVILEGE_TYPE          | IS_GRANTABLE |
+----------------------------+---------------+-------------------------+--------------+
| 'root'@'localhost'         | def           | SELECT                  | YES          |
| 'root'@'localhost'         | def           | INSERT                  | YES          |
| 'root'@'localhost'         | def           | UPDATE                  | YES          |
| 'root'@'localhost'         | def           | DELETE                  | YES          |
| 'root'@'localhost'         | def           | CREATE                  | YES          |
| 'root'@'localhost'         | def           | DROP                    | YES          |
| 'root'@'localhost'         | def           | RELOAD                  | YES          |
| 'root'@'localhost'         | def           | SHUTDOWN                | YES          |
| 'root'@'localhost'         | def           | PROCESS                 | YES          |
| 'root'@'localhost'         | def           | FILE                    | YES          |
| 'root'@'localhost'         | def           | REFERENCES              | YES          |
| 'root'@'localhost'         | def           | INDEX                   | YES          |
| 'root'@'localhost'         | def           | ALTER                   | YES          |
| 'root'@'localhost'         | def           | SHOW DATABASES          | YES          |
| 'root'@'localhost'         | def           | SUPER                   | YES          |
| 'root'@'localhost'         | def           | CREATE TEMPORARY TABLES | YES          |
| 'root'@'localhost'         | def           | LOCK TABLES             | YES          |
| 'root'@'localhost'         | def           | EXECUTE                 | YES          |
| 'root'@'localhost'         | def           | REPLICATION SLAVE       | YES          |
| 'root'@'localhost'         | def           | REPLICATION CLIENT      | YES          |
| 'root'@'localhost'         | def           | CREATE VIEW             | YES          |
| 'root'@'localhost'         | def           | SHOW VIEW               | YES          |
| 'root'@'localhost'         | def           | CREATE ROUTINE          | YES          |
| 'root'@'localhost'         | def           | ALTER ROUTINE           | YES          |
| 'root'@'localhost'         | def           | CREATE USER             | YES          |
| 'root'@'localhost'         | def           | EVENT                   | YES          |
| 'root'@'localhost'         | def           | TRIGGER                 | YES          |
| 'root'@'localhost'         | def           | CREATE TABLESPACE       | YES          |
| 'mysql.sys'@'localhost'    | def           | USAGE                   | NO           |
| 'repl'@'ip-172-31-5-140.ap-southeast-1.compute.internal' | def           | USAGE                   | NO           |
| 'repl'@'%.ap-southeast-1.compute.internal'    | def           | REPLICATION SLAVE       | NO           |
| 'amon'@'%'                 | def           | USAGE                   | NO           |
| 'rman'@'%'                 | def           | USAGE                   | NO           |
| 'hive'@'%'                 | def           | USAGE                   | NO           |
| 'sentry'@'%'               | def           | USAGE                   | NO           |
| 'nav'@'%'                  | def           | USAGE                   | NO           |
| 'navms'@'%'                | def           | USAGE                   | NO           |
| 'hue'@'%'                  | def           | USAGE                   | NO           |
| 'oozie'@'%'                | def           | USAGE                   | NO           |
+----------------------------+---------------+-------------------------+--------------+
39 rows in set (0.00 sec)
```

```sh
==========================================================================================================
MYSQL REPLICATION
==========================================================================================================
```
Add to /etc/my.cnf

Master
----------
[mysqld]
log-bin=mysql-bin
server-id=1	

Slave
----------
[mysqld]
server-id=2


sudo systemctl stop mysqld
sudo systemctl start mysqld


http://dev.mysql.com/doc/refman/5.7/en/replication-howto.html

172.31.5.137 cdh1.ap-southeast-1.compute.internal ip-172-31-5-137.ap-southeast-1.compute.internal
172.31.5.138 cdh2.ap-southeast-1.compute.internal ip-172-31-5-138.ap-southeast-1.compute.internal
172.31.5.139 ip-172-31-5-139.ap-southeast-1.compute.internal ip-172-31-5-139.ap-southeast-1.compute.internal
172.31.5.140 ip-172-31-5-140.ap-southeast-1.compute.internal ip-172-31-5-140.ap-southeast-1.compute.internal
172.31.5.141 cdh5.ap-southeast-1.compute.internal ip-172-31-5-141.ap-southeast-1.compute.internal


CREATE USER 'repl'@'%.ap-southeast-1.compute.internal' IDENTIFIED BY 'ZAQ!zaq112';
CREATE USER 'repl'@'ip-172-31-5-140.ap-southeast-1.compute.internal' IDENTIFIED BY 'ZAQ!zaq112';

GRANT REPLICATION SLAVE ON *.* TO 'repl'@'%.ap-southeast-1.compute.internal';

SET GLOBAL binlog_format = 'ROW'; 
FLUSH TABLES WITH READ LOCK;

Login to master (2nd session)
mysql> show master status;
+------------------+----------+--------------+------------------+-------------------+
| File             | Position | Binlog_Do_DB | Binlog_Ignore_DB | Executed_Gtid_Set |
+------------------+----------+--------------+------------------+-------------------+
| mysql-bin.000001 |      621 |              |                  |                   |
+------------------+----------+--------------+------------------+-------------------+
1 row in set (0.00 sec)
 unlock tables;
Query OK, 0 rows affected (0.00 sec)

logout of 2nd session

remove lock on 1st session  - unlock tables;

login to Replica

CHANGE MASTER TO MASTER_HOST='ip-172-31-5-139.ap-southeast-1.compute.internal',MASTER_USER='repl',MASTER_PASSWORD='ZAQ!zaq112',
MASTER_PORT=3306,MASTER_LOG_FILE='mysql-bin.000001',MASTER_LOG_POS=882;

start slave;

show slave status \G


mysql> show slave status \G
*************************** 1. row ***************************
               Slave_IO_State: Connecting to master
                  Master_Host: ip-172-31-5-139.ap-southeast-1.compute.internal
                  Master_User: repl
                  Master_Port: 3306
                Connect_Retry: 60
              Master_Log_File: mysql-bin.000001
          Read_Master_Log_Pos: 621
               Relay_Log_File: ip-172-31-5-140-relay-bin.000001
                Relay_Log_Pos: 4
        Relay_Master_Log_File: mysql-bin.000001
             Slave_IO_Running: Connecting
            Slave_SQL_Running: Yes
              Replicate_Do_DB:
          Replicate_Ignore_DB:
           Replicate_Do_Table:
       Replicate_Ignore_Table:
      Replicate_Wild_Do_Table:
  Replicate_Wild_Ignore_Table:
                   Last_Errno: 0
                   Last_Error:
                 Skip_Counter: 0
          Exec_Master_Log_Pos: 621
              Relay_Log_Space: 154
              Until_Condition: None
               Until_Log_File:
                Until_Log_Pos: 0
           Master_SSL_Allowed: No
           Master_SSL_CA_File:
           Master_SSL_CA_Path:
              Master_SSL_Cert:
            Master_SSL_Cipher:
               Master_SSL_Key:
        Seconds_Behind_Master: NULL
Master_SSL_Verify_Server_Cert: No
                Last_IO_Errno: 2003
                Last_IO_Error: error connecting to master 'repl@ip-172-31-5-139.ap-southeast-1.compute.internal:3306' - retry                                                                         -time: 60  retries: 1
               Last_SQL_Errno: 0
               Last_SQL_Error:
  Replicate_Ignore_Server_Ids:
             Master_Server_Id: 0
                  Master_UUID:
             Master_Info_File: /var/lib/mysql/master.info
                    SQL_Delay: 0
          SQL_Remaining_Delay: NULL
      Slave_SQL_Running_State: Slave has read all relay log; waiting for more updates
           Master_Retry_Count: 86400
                  Master_Bind:
      Last_IO_Error_Timestamp: 161205 18:21:35
     Last_SQL_Error_Timestamp:
               Master_SSL_Crl:
           Master_SSL_Crlpath:
           Retrieved_Gtid_Set:
            Executed_Gtid_Set:
                Auto_Position: 0
         Replicate_Rewrite_DB:
                 Channel_Name:
           Master_TLS_Version:
1 row in set (0.00 sec)


STOP SLAVE;
RESET SLAVE ALL:
```
