- Report the latest available version of the API
[root@ip-172-31-44-17 cloudera-scm-server]# curl -u fpcel:FPCEL#ClouderaSEB# "http://ec2-54-154-64-92.eu-west-1.compute.amazonaws.com:7180/api/version"
v14
- Report the CM version
[root@ip-172-31-44-17 cloudera-scm-server]# curl -u fpcel:FPCEL#ClouderaSEB# "http://ec2-54-154-64-92.eu-west-1.compute.amazonaws.com:7180/api/v12/cm/version"
{
  "version" : "5.9.2",
  "buildUser" : "jenkins",
  "buildTimestamp" : "20170330-1814",
  "gitHash" : "822da28bff818f57fc1bfc3eafe3a550300ef1b0",
  "snapshot" : false
}[
- List all CM users
[root@ip-172-31-44-17 cloudera-scm-server]# curl -u fpcel:FPCEL#ClouderaSEB# "http://ec2-54-154-64-92.eu-west-1.compute.amazonaws.com:7180/api/v12/users"
{
  "items" : [ {
    "name" : "admin",
    "roles" : [ "ROLE_LIMITED" ]
  }, {
    "name" : "fpcel",
    "roles" : [ "ROLE_ADMIN" ]
  }, {
    "name" : "minotaur",
    "roles" : [ "ROLE_CONFIGURATOR" ]
  } ]
}
- Report the database server in use by CM