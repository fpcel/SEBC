- Authenticate your user as a Kerberos principal:
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
- Use beeline to confirm your principal sees no tables
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
- Create a Sentry role with full authorization
```
[root@ip-172-31-47-47 ~]# beeline
Beeline version 1.1.0-cdh5.8.3 by Apache Hive
beeline> !connect jdbc:hive2://ip-172-31-44-17.eu-west-1.compute.internal:10000/default;principal=hive/ip-172-31-44-17.eu-west-1.compute.internal@FPCEL.COM
scan complete in 3ms
Connecting to jdbc:hive2://ip-172-31-44-17.eu-west-1.compute.internal:10000/default;principal=hive/ip-172-31-44-17.eu-west-1.compute.internal@FPCEL.COM
Enter username for jdbc:hive2://ip-172-31-44-17.eu-west-1.compute.internal:10000/default;principal=hive/ip-172-31-44-17.eu-west-1.compute.internal@FPCEL.COM: fpcel
Enter password for jdbc:hive2://ip-172-31-44-17.eu-west-1.compute.internal:10000/default;principal=hive/ip-172-31-44-17.eu-west-1.compute.internal@FPCEL.COM: *******
Connected to: Apache Hive (version 1.1.0-cdh5.8.3)
Driver: Hive JDBC (version 1.1.0-cdh5.8.3)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://ip-172-31-44-17.eu-west-1.com> CREATE ROLE sentry_admin;
INFO  : Compiling command(queryId=hive_20170608081919_d2d3b1d3-0410-4aac-baec-4b3d0ff5acea): CREATE ROLE sentry_admin
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20170608081919_d2d3b1d3-0410-4aac-baec-4b3d0ff5acea); Time taken: 0.649 seconds
INFO  : Executing command(queryId=hive_20170608081919_d2d3b1d3-0410-4aac-baec-4b3d0ff5acea): CREATE ROLE sentry_admin
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170608081919_d2d3b1d3-0410-4aac-baec-4b3d0ff5acea); Time taken: 0.839 seconds
INFO  : OK
No rows affected (2.761 seconds)
0: jdbc:hive2://ip-172-31-44-17.eu-west-1.com> GRANT ALL ON SERVER server1 TO ROLE sentry_admin;
INFO  : Compiling command(queryId=hive_20170608081919_9dbb8347-8ad4-4ae3-a400-bdf4be899a68): GRANT ALL ON SERVER server1 TO ROLE sentry_admin
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20170608081919_9dbb8347-8ad4-4ae3-a400-bdf4be899a68); Time taken: 0.144 seconds
INFO  : Executing command(queryId=hive_20170608081919_9dbb8347-8ad4-4ae3-a400-bdf4be899a68): GRANT ALL ON SERVER server1 TO ROLE sentry_admin
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170608081919_9dbb8347-8ad4-4ae3-a400-bdf4be899a68); Time taken: 0.105 seconds
INFO  : OK
No rows affected (0.265 seconds)
0: jdbc:hive2://ip-172-31-44-17.eu-west-1.com> GRANT ROLE sentry_admin TO GROUP fpcel;
INFO  : Compiling command(queryId=hive_20170608082020_29fb7207-15f6-4ab0-9d09-404513534756): GRANT ROLE sentry_admin TO GROUP fpcel
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20170608082020_29fb7207-15f6-4ab0-9d09-404513534756); Time taken: 0.083 seconds
INFO  : Executing command(queryId=hive_20170608082020_29fb7207-15f6-4ab0-9d09-404513534756): GRANT ROLE sentry_admin TO GROUP fpcel
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170608082020_29fb7207-15f6-4ab0-9d09-404513534756); Time taken: 0.082 seconds
INFO  : OK
No rows affected (0.176 seconds)
0: jdbc:hive2://ip-172-31-44-17.eu-west-1.com> show tables;
INFO  : Compiling command(queryId=hive_20170608082020_d148a2c6-515f-4f1e-a5d2-a67551ff18bf): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20170608082020_d148a2c6-515f-4f1e-a5d2-a67551ff18bf); Time taken: 0.284 seconds
INFO  : Executing command(queryId=hive_20170608082020_d148a2c6-515f-4f1e-a5d2-a67551ff18bf): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170608082020_d148a2c6-515f-4f1e-a5d2-a67551ff18bf); Time taken: 0.264 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| customers  |
| sample_07  |
| sample_08  |
| web_logs   |
+------------+--+
4 rows selected (0.684 seconds)
```
- Create additional test users (all cluster nodes)
```
sudo groupadd selector
sudo groupadd inserters
sudo useradd -u 1100 -g selector george
sudo useradd -u 1200 -g inserters ferdinand
```
- Create additional test users (on Kerberos Server)
```
kadmin.local
addprinc george
addprinc ferdinand
``` 
- Create test roles
```
0: jdbc:hive2://ip-172-31-44-17.eu-west-1.com> CREATE ROLE reads;
INFO  : Compiling command(queryId=hive_20170608083131_5b5a2680-754a-4f27-9571-9a5f7c9b6f73): CREATE ROLE reads
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20170608083131_5b5a2680-754a-4f27-9571-9a5f7c9b6f73); Time taken: 0.077 seconds
INFO  : Executing command(queryId=hive_20170608083131_5b5a2680-754a-4f27-9571-9a5f7c9b6f73): CREATE ROLE reads
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170608083131_5b5a2680-754a-4f27-9571-9a5f7c9b6f73); Time taken: 0.047 seconds
INFO  : OK
No rows affected (0.185 seconds)
0: jdbc:hive2://ip-172-31-44-17.eu-west-1.com> CREATE ROLE writes;
INFO  : Compiling command(queryId=hive_20170608083131_d9082e5e-0887-4e9b-a0b7-dd51c9028108): CREATE ROLE writes
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20170608083131_d9082e5e-0887-4e9b-a0b7-dd51c9028108); Time taken: 0.056 seconds
INFO  : Executing command(queryId=hive_20170608083131_d9082e5e-0887-4e9b-a0b7-dd51c9028108): CREATE ROLE writes
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170608083131_d9082e5e-0887-4e9b-a0b7-dd51c9028108); Time taken: 0.035 seconds
INFO  : OK
No rows affected (0.102 seconds)
```
- Grant read privilege for all tables to reads
```
0: jdbc:hive2://ip-172-31-44-17.eu-west-1.com> GRANT SELECT ON DATABASE default TO ROLE reads;
INFO  : Compiling command(queryId=hive_20170608083232_b0008075-d342-45b1-98a9-f2f0bed282f7): GRANT SELECT ON DATABASE default TO ROLE reads
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20170608083232_b0008075-d342-45b1-98a9-f2f0bed282f7); Time taken: 0.069 seconds
INFO  : Executing command(queryId=hive_20170608083232_b0008075-d342-45b1-98a9-f2f0bed282f7): GRANT SELECT ON DATABASE default TO ROLE reads
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170608083232_b0008075-d342-45b1-98a9-f2f0bed282f7); Time taken: 0.044 seconds
INFO  : OK
No rows affected (0.122 seconds)
0: jdbc:hive2://ip-172-31-44-17.eu-west-1.com> GRANT ROLE reads TO GROUP selector;
INFO  : Compiling command(queryId=hive_20170608083232_118218d4-05c5-417a-8b20-bdd42d724991): GRANT ROLE reads TO GROUP selector
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20170608083232_118218d4-05c5-417a-8b20-bdd42d724991); Time taken: 0.07 seconds
INFO  : Executing command(queryId=hive_20170608083232_118218d4-05c5-417a-8b20-bdd42d724991): GRANT ROLE reads TO GROUP selector
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170608083232_118218d4-05c5-417a-8b20-bdd42d724991); Time taken: 0.031 seconds
INFO  : OK
No rows affected (0.111 seconds)
```
- Grant read privilege for default.sample07 only to writes
```
0: jdbc:hive2://ip-172-31-44-17.eu-west-1.com> REVOKE ALL ON DATABASE default FROM ROLE writes;
INFO  : Compiling command(queryId=hive_20170608083333_d53bbfb0-1f16-4872-8b65-4a0a70bc373b): REVOKE ALL ON DATABASE default FROM ROLE writes
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20170608083333_d53bbfb0-1f16-4872-8b65-4a0a70bc373b); Time taken: 0.06 seconds
INFO  : Executing command(queryId=hive_20170608083333_d53bbfb0-1f16-4872-8b65-4a0a70bc373b): REVOKE ALL ON DATABASE default FROM ROLE writes
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170608083333_d53bbfb0-1f16-4872-8b65-4a0a70bc373b); Time taken: 0.091 seconds
INFO  : OK
No rows affected (0.164 seconds)
0: jdbc:hive2://ip-172-31-44-17.eu-west-1.com> GRANT SELECT ON default.sample_07 TO ROLE writes;
INFO  : Compiling command(queryId=hive_20170608083333_2a47ddda-4987-4a5b-ab17-afdf27557686): GRANT SELECT ON default.sample_07 TO ROLE writes
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20170608083333_2a47ddda-4987-4a5b-ab17-afdf27557686); Time taken: 0.078 seconds
INFO  : Executing command(queryId=hive_20170608083333_2a47ddda-4987-4a5b-ab17-afdf27557686): GRANT SELECT ON default.sample_07 TO ROLE writes
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170608083333_2a47ddda-4987-4a5b-ab17-afdf27557686); Time taken: 0.055 seconds
INFO  : OK
No rows affected (0.144 seconds)
0: jdbc:hive2://ip-172-31-44-17.eu-west-1.com> GRANT ROLE writes TO GROUP inserters;
INFO  : Compiling command(queryId=hive_20170608083333_f69b6028-d0b4-4e74-a9a1-b1ac01818b5c): GRANT ROLE writes TO GROUP inserters
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20170608083333_f69b6028-d0b4-4e74-a9a1-b1ac01818b5c); Time taken: 0.061 seconds
INFO  : Executing command(queryId=hive_20170608083333_f69b6028-d0b4-4e74-a9a1-b1ac01818b5c): GRANT ROLE writes TO GROUP inserters
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170608083333_f69b6028-d0b4-4e74-a9a1-b1ac01818b5c); Time taken: 0.03 seconds
INFO  : OK
No rows affected (0.101 seconds)
```
- kinit as george, then login to beeline
```
[root@ip-172-31-47-47 ~]# kinit george
Password for george@FPCEL.COM:
[root@ip-172-31-47-47 ~]# beeline
```
```
0: jdbc:hive2://ip-172-31-44-17.eu-west-1.com> show tables;
INFO  : Compiling command(queryId=hive_20170608083636_7b246bd7-cf2f-488b-a7ca-6855146d42c8): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20170608083636_7b246bd7-cf2f-488b-a7ca-6855146d42c8); Time taken: 0.071 seconds
INFO  : Executing command(queryId=hive_20170608083636_7b246bd7-cf2f-488b-a7ca-6855146d42c8): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170608083636_7b246bd7-cf2f-488b-a7ca-6855146d42c8); Time taken: 0.156 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| customers  |
| sample_07  |
| sample_08  |
| web_logs   |
+------------+--+
4 rows selected (0.354 seconds)
```
- Repeat for ferdinand
```
[root@ip-172-31-47-47 ~]# kinit ferdinand
Password for ferdinand@FPCEL.COM:
[root@ip-172-31-47-47 ~]# beeline
```
```
0: jdbc:hive2://ip-172-31-44-17.eu-west-1.com> show tables;
INFO  : Compiling command(queryId=hive_20170608083939_84de5f38-ebc3-4ed6-9d43-a75ab5cc75d6): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20170608083939_84de5f38-ebc3-4ed6-9d43-a75ab5cc75d6); Time taken: 0.069 seconds
INFO  : Executing command(queryId=hive_20170608083939_84de5f38-ebc3-4ed6-9d43-a75ab5cc75d6): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170608083939_84de5f38-ebc3-4ed6-9d43-a75ab5cc75d6); Time taken: 0.147 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| sample_07  |
+------------+--+
1 row selected (0.34 seconds)
```