1- OS memory and vcores
```
Reduced the memory to 8GB and vcores to 1 as typically is enough to the most part of the Operating systems.
Based on the Cloudera recommendations
```
2- YARM RM Properties
```
Changed the parameters yarn.scheduler.maximum-allocation-vcores to 16 and yarn.scheduler.maximum-allocation-mb to 119808
to match the node resources as advised on Cloudera Documentation
Reference: https://www.cloudera.com/documentation/enterprise/5-8-x/topics/cm_mc_yarn_service.html
```
3- Task container settings
```
Reduced the JVM Heapsize to 75% of memory-mb parameters as per the Cloudera recommendation
mapreduce.map.java.opts.max.heap=768
mapreduce.reduce.java.opts.max.heap=768
Also changed the mininums to the following values:
mapreduce.map.memory.mb=1024
mapreduce.map.cpu.vcores=1
This way the applications will request as minimum of 1024 MB and 1 core to start.
```
4- MapReduce AM Settings
```
The parameter yarn.app.mapreduce.am.resource.mb should be expressed in MB, so changed it to 1024.
yarn.app.mapreduce.am.resource.mb=1024
Also changed the JVM Heap to 75%
yarn.app.mapreduce.am.resource.command-opts	768
```
5- Gateway Settings
```
Changed the heap size parameters to 75% of the memory ones:
-D mapreduce.map.memory.mb=2048
-D mapreduce.reduce.memory.mb=4096
-D mapreduce.map.java.opts.max.heap=1536
-D mapreduce.reduce.java.opts.max.heap=2048
Also set as undefined the parameter mapreduce.job.maps as in YARN as well if you are using MapReduce based frameworks, the number of mappers should depend on input splits.
```
- What criteria affects workload factor? What does a value of 1, 2, or 4 signify?
```
The workload factor should affect the ratio between CPU/Memory/IO. 
For instance, the workload factor should impact the number of vcores based on the number of physical CPUs. 
Also, it should take into consideration the kind of usage the cluster will execute (ETL tasks, Machine Learning, Natural Language processing).
```