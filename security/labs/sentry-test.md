```
[root@ip-172-31-44-17 ~]# kinit fpcel@FPCEL.COM
Password for fpcel@FPCEL.COM:
```
```
[root@ip-172-31-44-17 ~]# klist
Ticket cache: FILE:/tmp/krb5cc_0
Default principal: fpcel@FPCEL.COM

Valid starting     Expires            Service principal
06/07/17 23:16:12  06/08/17 23:16:12  krbtgt/FPCEL.COM@FPCEL.COM
        renew until 06/14/17 23:16:12
```
```
[root@ip-172-31-44-17 ~]# beeline
Beeline version 1.1.0-cdh5.8.3 by Apache Hive
beeline> !connect jdbc:hive2://ip-172-31-44-17.eu-west-1.compute.internal:10000/default;principal=hive/ip-172-31-44-17.eu-west-1.compute.internal@FPCEL.COM
Connecting to jdbc:hive2://ip-172-31-44-17.eu-west-1.compute.internal:10000/default;principal=hive/ip-172-31-44-17.eu-west-1.compute.internal@FPCEL.COM
Enter username for jdbc:hive2://ip-172-31-44-17.eu-west-1.compute.internal:10000/default;principal=hive/ip-172-31-44-17.eu-west-1.compute.internal@FPCEL.COM: fpcel
Enter password for jdbc:hive2://ip-172-31-44-17.eu-west-1.compute.internal:10000/default;principal=hive/ip-172-31-44-17.eu-west-1.compute.internal@FPCEL.COM: ********
Connected to: Apache Hive (version 1.1.0-cdh5.8.3)
Driver: Hive JDBC (version 1.1.0-cdh5.8.3)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://ip-172-31-44-17.eu-west-1.com> show tables;
INFO  : Compiling command(queryId=hive_20170607232121_2429c045-41b0-4e2a-8bca-ce4118244bc7): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20170607232121_2429c045-41b0-4e2a-8bca-ce4118244bc7); Time taken: 0.064 seconds
INFO  : Executing command(queryId=hive_20170607232121_2429c045-41b0-4e2a-8bca-ce4118244bc7): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170607232121_2429c045-41b0-4e2a-8bca-ce4118244bc7); Time taken: 0.143 seconds
INFO  : OK
+-----------+--+
| tab_name  |
+-----------+--+
+-----------+--+
No rows selected (0.22 seconds)
```
