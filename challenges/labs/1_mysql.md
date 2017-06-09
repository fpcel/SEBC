- The hostname of your MySQL node
```
ip-172-31-16-137.eu-west-1.compute.internal
```
- The command and output for mysql --version
```
[root@ip-172-31-16-137 ~]# mysql --version
mysql  Ver 14.14 Distrib 5.5.56, for Linux (x86_64) using readline 5.1
```
- The command and output for listing MySQL databases
```
[root@ip-172-31-16-137 ~]# mysql -u root -p
mysql> show databases;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| hive               |
| hue                |
| mysql              |
| oozie              |
| performance_schema |
| rman               |
| scm                |
| sentry             |
+--------------------+
9 rows in set (0.00 sec)
```