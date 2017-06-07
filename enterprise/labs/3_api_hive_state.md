- Stop Service
```
curl -u yyyyy:ZZZZZ  -X POST -H "Content-Type:application/json" "http://ec2-54-154-64-92.eu-west-1.compute.amazonaws.com:7180/api/v12/clusters/fpcel/services/hive/commands/stop"
```
```json
{
  "id" : 453,
  "name" : "Stop",
  "startTime" : "2017-06-07T13:16:46.408Z",
  "active" : true,
  "serviceRef" : {
    "clusterName" : "cluster",
    "serviceName" : "hive"
  }
}
```
- Start Service
```
curl -u yyyyy:ZZZZZ  -X POST -H "Content-Type:application/json" "http://ec2-54-154-64-92.eu-west-1.compute.amazonaws.com:7180/api/v12/clusters/fpcel/services/hive/commands/start"
```
```json
{
  "id" : 457,
  "name" : "Start",
  "startTime" : "2017-06-07T13:17:54.214Z",
  "active" : true,
  "serviceRef" : {
    "clusterName" : "cluster",
    "serviceName" : "hive"
  }
}
```
- Check service state
```
curl -u yyyyy:ZZZZZ "http://ec2-54-154-64-92.eu-west-1.compute.amazonaws.com:7180/api/v12/clusters/fpcel/services/hive" | grep serviceState
```
```json
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
112   787    0   787    0     0  24733      0 --:--:-- --:--:-- --:--:-- 25387
  "serviceState" : "STARTED",
```
