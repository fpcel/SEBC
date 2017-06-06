- Create a 10 GB file using teragen:
```
time hadoop jar /opt/cloudera/parcels/CDH-5.8.3-1.cdh5.8.3.p0.2/jars/hadoop-examples.jar teragen -D dfs.block.size=33554432 -D mapreduce.job.maps=4 100000000 /user/fpcel/teragen-output-10gb
real    4m23.924s
user    0m6.488s
sys     0m0.770s
```
- Run the terasort command on this file:
```
time hadoop jar /opt/cloudera/parcels/CDH-5.8.3-1.cdh5.8.3.p0.2/jars/hadoop-examples.jar terasort /user/fpcel/teragen-output-10gb /user/fpcel/terasort-output
real    10m35.236s
user    0m10.920s
sys     0m1.128s

```