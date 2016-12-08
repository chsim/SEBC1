```
=======================================================================
/etc/yum.repos.d/cloudera-manager.repo
=======================================================================
```
[cloudera-manager]
name = Cloudera Manager, Version 5.8.2
baseurl = https://archive.cloudera.com/cm5/redhat/7/x86_64/cm/5.8.2/
gpgkey = https://archive.cloudera.com/redhat/cdh/RPM-GPG-KEY-cloudera
gpgcheck = 1

```
=======================================================================
SCM_PREPARE_DATABASE.SH
=======================================================================
```
sudo /usr/share/cmf/schema/scm_prepare_database.sh mysql amon amon 'ZAQ!zaq112'
sudo /usr/share/cmf/schema/scm_prepare_database.sh mysql rman rman 'ZAQ!zaq112'
sudo /usr/share/cmf/schema/scm_prepare_database.sh mysql metastore hive 'ZAQ!zaq112'
sudo /usr/share/cmf/schema/scm_prepare_database.sh mysql sentry sentry 'ZAQ!zaq112'
sudo /usr/share/cmf/schema/scm_prepare_database.sh mysql nav nav 'ZAQ!zaq112'
sudo /usr/share/cmf/schema/scm_prepare_database.sh mysql navms navms 'ZAQ!zaq112'

mysql> show grants for amon;
+------------------------------------------------+
| Grants for amon@%                              |
+------------------------------------------------+
| GRANT USAGE ON *.* TO 'amon'@'%'               |
| GRANT ALL PRIVILEGES ON `amon`.* TO 'amon'@'%' |
+------------------------------------------------+
2 rows in set (0.00 sec)

mysql> show grants for rman;
+------------------------------------------------+
| Grants for rman@%                              |
+------------------------------------------------+
| GRANT USAGE ON *.* TO 'rman'@'%'               |
| GRANT ALL PRIVILEGES ON `rman`.* TO 'rman'@'%' |
+------------------------------------------------+
2 rows in set (0.00 sec)

mysql> show grants for hive;
+-----------------------------------------------------+
| Grants for hive@%                                   |
+-----------------------------------------------------+
| GRANT USAGE ON *.* TO 'hive'@'%'                    |
| GRANT ALL PRIVILEGES ON `metastore`.* TO 'hive'@'%' |
+-----------------------------------------------------+
2 rows in set (0.00 sec)

mysql> show grants for sentry;
+----------------------------------------------------+
| Grants for sentry@%                                |
+----------------------------------------------------+
| GRANT USAGE ON *.* TO 'sentry'@'%'                 |
| GRANT ALL PRIVILEGES ON `sentry`.* TO 'sentry'@'%' |
+----------------------------------------------------+
2 rows in set (0.00 sec)

mysql> show grants for nav;
+----------------------------------------------+
| Grants for nav@%                             |
+----------------------------------------------+
| GRANT USAGE ON *.* TO 'nav'@'%'              |
| GRANT ALL PRIVILEGES ON `nav`.* TO 'nav'@'%' |
+----------------------------------------------+
2 rows in set (0.00 sec)

mysql> show grants for navms;
+--------------------------------------------------+
| Grants for navms@%                               |
+--------------------------------------------------+
| GRANT USAGE ON *.* TO 'navms'@'%'                |
| GRANT ALL PRIVILEGES ON `navms`.* TO 'navms'@'%' |
+--------------------------------------------------+
2 rows in set (0.01 sec)

