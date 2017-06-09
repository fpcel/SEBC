- Authentication
```
[jeremy@ip-172-31-19-203 ~]$ kinit
Password for jeremy@FPCEL.CO.UK:
```
- Pi command
```
[jeremy@ip-172-31-19-203 ~]$ time hadoop jar /opt/cloudera/parcels/CDH/jars/hadoop-examples.jar pi 4 100000
Number of Maps  = 4
Samples per Map = 100000
Wrote input for Map #0
Wrote input for Map #1
Wrote input for Map #2
Wrote input for Map #3
Starting Job
17/06/09 10:38:13 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-16-137.eu-west-1.compute.internal/172.31.16.137:8032
17/06/09 10:38:13 INFO hdfs.DFSClient: Created token for jeremy: HDFS_DELEGATION_TOKEN owner=jeremy@FPCEL.CO.UK, renewer=yarn, realUser=, issueDate=1497004693702, maxDate=1497609493702, sequenceNumber=2, masterKeyId=2 on 172.31.16.137:8020
17/06/09 10:38:13 INFO security.TokenCache: Got dt for hdfs://ip-172-31-16-137.eu-west-1.compute.internal:8020; Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.16.137:8020, Ident: (token for jeremy: HDFS_DELEGATION_TOKEN owner=jeremy@FPCEL.CO.UK, renewer=yarn, realUser=, issueDate=1497004693702, maxDate=1497609493702, sequenceNumber=2, masterKeyId=2)
17/06/09 10:38:13 INFO input.FileInputFormat: Total input paths to process : 4
17/06/09 10:38:13 INFO mapreduce.JobSubmitter: number of splits:4
17/06/09 10:38:14 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1497003849298_0002
17/06/09 10:38:14 INFO mapreduce.JobSubmitter: Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.16.137:8020, Ident: (token for jeremy: HDFS_DELEGATION_TOKEN owner=jeremy@FPCEL.CO.UK, renewer=yarn, realUser=, issueDate=1497004693702, maxDate=1497609493702, sequenceNumber=2, masterKeyId=2)
17/06/09 10:38:14 INFO impl.YarnClientImpl: Submitted application application_1497003849298_0002
17/06/09 10:38:14 INFO mapreduce.Job: The url to track the job: http://ip-172-31-16-137.eu-west-1.compute.internal:8088/proxy/application_1497003849298_0002/
17/06/09 10:38:14 INFO mapreduce.Job: Running job: job_1497003849298_0002
17/06/09 10:38:22 INFO mapreduce.Job: Job job_1497003849298_0002 running in uber mode : false
17/06/09 10:38:22 INFO mapreduce.Job:  map 0% reduce 0%
17/06/09 10:38:34 INFO mapreduce.Job:  map 100% reduce 0%
17/06/09 10:38:39 INFO mapreduce.Job:  map 100% reduce 100%
17/06/09 10:38:39 INFO mapreduce.Job: Job job_1497003849298_0002 completed successfully
17/06/09 10:38:39 INFO mapreduce.Job: Counters: 49
        File System Counters
                FILE: Number of bytes read=68
                FILE: Number of bytes written=632068
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=1196
                HDFS: Number of bytes written=215
                HDFS: Number of read operations=19
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=3
        Job Counters
                Launched map tasks=4
                Launched reduce tasks=1
                Data-local map tasks=4
                Total time spent by all maps in occupied slots (ms)=33922
                Total time spent by all reduces in occupied slots (ms)=3295
                Total time spent by all map tasks (ms)=33922
                Total time spent by all reduce tasks (ms)=3295
                Total vcore-seconds taken by all map tasks=33922
                Total vcore-seconds taken by all reduce tasks=3295
                Total megabyte-seconds taken by all map tasks=34736128
                Total megabyte-seconds taken by all reduce tasks=3374080
        Map-Reduce Framework
                Map input records=4
                Map output records=8
                Map output bytes=72
                Map output materialized bytes=140
                Input split bytes=724
                Combine input records=0
                Combine output records=0
                Reduce input groups=2
                Reduce shuffle bytes=140
                Reduce input records=8
                Reduce output records=0
                Spilled Records=16
                Shuffled Maps =4
                Failed Shuffles=0
                Merged Map outputs=4
                GC time elapsed (ms)=472
                CPU time spent (ms)=4300
                Physical memory (bytes) snapshot=2012180480
                Virtual memory (bytes) snapshot=13871906816
                Total committed heap usage (bytes)=2129657856
        Shuffle Errors
                BAD_ID=0
                CONNECTION=0
                IO_ERROR=0
                WRONG_LENGTH=0
                WRONG_MAP=0
                WRONG_REDUCE=0
        File Input Format Counters
                Bytes Read=472
        File Output Format Counters
                Bytes Written=97
Job Finished in 25.684 seconds
Estimated value of Pi is 3.14161000000000000000

real    0m28.909s
user    0m7.836s
sys     0m0.858s
```