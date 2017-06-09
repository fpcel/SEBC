- Command and output for hdfs dfs -ls /user
```
[root@ip-172-31-24-220 ~]# hdfs dfs -ls /user
Found 6 items
drwxrwxrwx   - mapred  hadoop                0 2017-06-09 09:44 /user/history
drwxrwxr-t   - hive    hive                  0 2017-06-09 09:45 /user/hive
drwxrwxr-x   - hue     hue                   0 2017-06-09 09:46 /user/hue
drwxr-xr-x   - jeremy  labour                0 2017-06-09 09:48 /user/jeremy
drwxrwxr-x   - oozie   oozie                 0 2017-06-09 09:46 /user/oozie
drwxr-xr-x   - theresa conservative          0 2017-06-09 09:48 /user/theresa

```
- The output from the CM API call ../api/v14/hosts
```
[root@ip-172-31-24-220 ~]# curl -u admin:XXXXXXX 'ec2-54-229-201-172.eu-west-1.compute.amazonaws.com:7180/api/v14/hosts'
{
  "items" : [ {
    "hostId" : "eb2f4b57-f18d-4f2d-ae3e-8b1c5940b10c",
    "ipAddress" : "172.31.16.137",
    "hostname" : "ip-172-31-16-137.eu-west-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-24-220.eu-west-1.compute.internal:7180/cmf/hostRedirect/eb2f4b57-f18d-4f2d-ae3e-8b1c5940b10c",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 15740506112
  }, {
    "hostId" : "8eb4af1d-4d3e-4690-b672-169788f70467",
    "ipAddress" : "172.31.17.217",
    "hostname" : "ip-172-31-17-217.eu-west-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-24-220.eu-west-1.compute.internal:7180/cmf/hostRedirect/8eb4af1d-4d3e-4690-b672-169788f70467",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 15740506112
  }, {
    "hostId" : "d2bd9069-0aae-472a-a4a5-ee4a75705833",
    "ipAddress" : "172.31.19.203",
    "hostname" : "ip-172-31-19-203.eu-west-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-24-220.eu-west-1.compute.internal:7180/cmf/hostRedirect/d2bd9069-0aae-472a-a4a5-ee4a75705833",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 15740506112
  }, {
    "hostId" : "57f77a31-1346-4f1e-8634-a8f35fb8cb6b",
    "ipAddress" : "172.31.19.96",
    "hostname" : "ip-172-31-19-96.eu-west-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-24-220.eu-west-1.compute.internal:7180/cmf/hostRedirect/57f77a31-1346-4f1e-8634-a8f35fb8cb6b",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 15740506112
  }, {
    "hostId" : "5534d38b-ee16-400d-98bf-971e2a5203b7",
    "ipAddress" : "172.31.24.220",
    "hostname" : "ip-172-31-24-220.eu-west-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-24-220.eu-west-1.compute.internal:7180/cmf/hostRedirect/5534d38b-ee16-400d-98bf-971e2a5203b7",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 15740506112
  } ]
}
```