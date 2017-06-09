- Login to beeline with the principal for theresa. List the result of SHOW TABLES
```
Used Code:

    CREATE ROLE politican1;
	GRANT ALL ON DATABASE default TO ROLE politican1;
	GRANT ROLE politican1 TO GROUP conservative;
	
	CREATE ROLE politican2;
	GRANT SELECT ON default.sample_07 TO ROLE politican2;
	GRANT SELECT ON default.sample_08 TO ROLE politican2;
	GRANT ROLE politican2 TO GROUP labour;
```
```
0: jdbc:hive2://ip-172-31-16-137.eu-west-1.co> show tables;
INFO  : Compiling command(queryId=hive_20170609110808_f37a7213-e491-46ed-ae9d-2b733e0b0566): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20170609110808_f37a7213-e491-46ed-ae9d-2b733e0b0566); Time taken: 0.067 seconds
INFO  : Executing command(queryId=hive_20170609110808_f37a7213-e491-46ed-ae9d-2b733e0b0566): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170609110808_f37a7213-e491-46ed-ae9d-2b733e0b0566); Time taken: 0.112 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| customers  |
| sample_07  |
| sample_08  |
| web_logs   |
+------------+--+
4 rows selected (0.201 seconds)
```
- Login again to beeline as the principal for jeremy. List the result of SHOW TABLES
```
Used Code:	
	CREATE ROLE politican2;
	GRANT SELECT ON default.sample_07 TO ROLE politican2;
	GRANT SELECT ON default.sample_08 TO ROLE politican2;
	GRANT ROLE politican2 TO GROUP labour;
```
```
[jeremy@ip-172-31-16-137 ~]$ kinit
Password for jeremy@FPCEL.CO.UK:
[jeremy@ip-172-31-16-137 ~]$ beeline
Java HotSpot(TM) 64-Bit Server VM warning: ignoring option MaxPermSize=512M; support was removed in 8.0
Java HotSpot(TM) 64-Bit Server VM warning: ignoring option MaxPermSize=512M; support was removed in 8.0
Beeline version 1.1.0-cdh5.10.1 by Apache Hive
beeline> !connect jdbc:hive2://ip-172-31-16-137.eu-west-1.compute.internal:10000/default;principal=hive/ip-172-31-16-137.eu-west-1.compute.internal@FPCEL.CO.UK
scan complete in 2ms
Connecting to jdbc:hive2://ip-172-31-16-137.eu-west-1.compute.internal:10000/default;principal=hive/ip-172-31-16-137.eu-west-1.compute.internal@FPCEL.CO.UK
Connected to: Apache Hive (version 1.1.0-cdh5.10.1)
Driver: Hive JDBC (version 1.1.0-cdh5.10.1)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://ip-172-31-16-137.eu-west-1.co> show tables;
INFO  : Compiling command(queryId=hive_20170609111414_103cd603-d1d4-44ac-aadf-30b664afd174): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20170609111414_103cd603-d1d4-44ac-aadf-30b664afd174); Time taken: 0.063 seconds
INFO  : Executing command(queryId=hive_20170609111414_103cd603-d1d4-44ac-aadf-30b664afd174): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170609111414_103cd603-d1d4-44ac-aadf-30b664afd174); Time taken: 0.128 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| sample_07  |
| sample_08  |
+------------+--+
2 rows selected (0.294 seconds)
```