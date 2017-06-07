- What is ubertask optimization?
```
Ubertask optimization is used to run small tasks. It happens when the Application Master uses its own JVM to run Map and Reduce tasks, 
reducing the overhead on container allocation, since YARN only allocates a container for the AM.
```
- Where in CM is the Kerberos Security Realm value displayed?
```
Administration > Settings > Kerberos > default_realm
```
- Which CDH service(s) host a property for enabling Kerberos authentication?
```
HDFS
MapReduce
YARN
Accumulo
Flume
HBase
Hue
Impala
Oozie
Pig
Search
Sentry
Spark
Sqoop
Sqoop2
Zookeeper
Reference: https://www.cloudera.com/documentation/enterprise/5-8-x/topics/sg_auth_overview.html
```
- How do you upgrade the CM agents?
```
1- Start by stopping the services
2- Upgrade the repos if necessary
3- Update the packages for the cloudera-scm-server, cloudera-scm-daemons and cloudera-scm-agent
4- Restart the server
5- Log in to the Cloudera Manager Admin Console. The Upgrade Wizard displays
6- Upgrade the Agent software using Cloudera Manager
More detail on Step 7 from https://www.cloudera.com/documentation/enterprise/5-8-x/topics/cm_ag_ug_cm5.html#concept_gs4_bsg_xw
```
- Give the tsquery statement used to chart Hue's CPU utilization?
```
select cpu_system_rate + cpu_user_rate where category=ROLE and serviceName=$SERVICENAME
$SERVICENAME = hue  $CLUSTERID = 1
select cpu_system_rate + cpu_user_rate where category=ROLE and serviceName=hue 
```
- Name all the roles that make up the Hive service
```
HiveServer2
Gateway
Hive Metastore Server
```
- What steps must be completed before integrating Cloudera Manager with Kerberos?
```
1- First install and setup KDC using packages: krb5-server, krb5-libs and krb5-workstation
2- Config the Kerberos Realm
3- Install openldap-clients on the Cloudera Manager Server host
4- Install krb5-workstation, krb5-libs on ALL hosts
5- Create an account for Cloudera Manager that has the permissions to create other accounts in the KDC 
```