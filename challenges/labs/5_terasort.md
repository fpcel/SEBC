- Authentication
```
[theresa@ip-172-31-19-203 ~]$ kinit
Password for theresa@FPCEL.CO.UK:
```
- Terasort
```
[theresa@ip-172-31-19-203 ~]$ time hadoop jar /opt/cloudera/parcels/CDH/jars/hadoop-examples.jar terasort /user/theresa/tgen512m /user/theresa/tgen512m_sort
17/06/09 10:31:17 INFO terasort.TeraSort: starting
17/06/09 10:31:19 INFO hdfs.DFSClient: Created token for theresa: HDFS_DELEGATION_TOKEN owner=theresa@FPCEL.CO.UK, renewer=yarn, realUser=, issueDate=1497004278983, maxDate=1497609078983, sequenceNumber=1, masterKeyId=2 on 172.31.16.137:8020
17/06/09 10:31:19 INFO security.TokenCache: Got dt for hdfs://ip-172-31-16-137.eu-west-1.compute.internal:8020; Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.16.137:8020, Ident: (token for theresa: HDFS_DELEGATION_TOKEN owner=theresa@FPCEL.CO.UK, renewer=yarn, realUser=, issueDate=1497004278983, maxDate=1497609078983, sequenceNumber=1, masterKeyId=2)
17/06/09 10:31:19 INFO input.FileInputFormat: Total input paths to process : 6
Spent 417ms computing base-splits.
Spent 5ms computing TeraScheduler splits.
Computing input splits took 423ms
Sampling 10 splits of 156
Making 8 from 100000 sampled records
Computing parititions took 769ms
Spent 1195ms computing partitions.
17/06/09 10:31:20 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-16-137.eu-west-1.compute.internal/172.31.16.137:8032
17/06/09 10:31:20 INFO mapreduce.JobSubmitter: number of splits:156
17/06/09 10:31:20 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1497003849298_0001
17/06/09 10:31:20 INFO mapreduce.JobSubmitter: Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.16.137:8020, Ident: (token for theresa: HDFS_DELEGATION_TOKEN owner=theresa@FPCEL.CO.UK, renewer=yarn, realUser=, issueDate=1497004278983, maxDate=1497609078983, sequenceNumber=1, masterKeyId=2)
17/06/09 10:31:21 INFO impl.YarnClientImpl: Submitted application application_1497003849298_0001
17/06/09 10:31:21 INFO mapreduce.Job: The url to track the job: http://ip-172-31-16-137.eu-west-1.compute.internal:8088/proxy/application_1497003849298_0001/
17/06/09 10:31:21 INFO mapreduce.Job: Running job: job_1497003849298_0001
17/06/09 10:31:32 INFO mapreduce.Job: Job job_1497003849298_0001 running in uber mode : false
17/06/09 10:31:32 INFO mapreduce.Job:  map 0% reduce 0%
17/06/09 10:31:44 INFO mapreduce.Job:  map 1% reduce 0%
17/06/09 10:31:45 INFO mapreduce.Job:  map 2% reduce 0%
17/06/09 10:31:46 INFO mapreduce.Job:  map 3% reduce 0%
17/06/09 10:31:49 INFO mapreduce.Job:  map 5% reduce 0%
17/06/09 10:31:53 INFO mapreduce.Job:  map 9% reduce 0%
17/06/09 10:31:54 INFO mapreduce.Job:  map 10% reduce 0%
17/06/09 10:31:55 INFO mapreduce.Job:  map 11% reduce 0%
17/06/09 10:31:59 INFO mapreduce.Job:  map 13% reduce 0%
17/06/09 10:32:01 INFO mapreduce.Job:  map 14% reduce 0%
17/06/09 10:32:04 INFO mapreduce.Job:  map 15% reduce 0%
17/06/09 10:32:05 INFO mapreduce.Job:  map 17% reduce 0%
17/06/09 10:32:06 INFO mapreduce.Job:  map 19% reduce 0%
17/06/09 10:32:09 INFO mapreduce.Job:  map 22% reduce 0%
17/06/09 10:32:14 INFO mapreduce.Job:  map 23% reduce 0%
17/06/09 10:32:15 INFO mapreduce.Job:  map 24% reduce 0%
17/06/09 10:32:16 INFO mapreduce.Job:  map 26% reduce 0%
17/06/09 10:32:19 INFO mapreduce.Job:  map 29% reduce 0%
17/06/09 10:32:22 INFO mapreduce.Job:  map 30% reduce 0%
17/06/09 10:32:23 INFO mapreduce.Job:  map 31% reduce 0%
17/06/09 10:32:24 INFO mapreduce.Job:  map 33% reduce 0%
17/06/09 10:32:29 INFO mapreduce.Job:  map 36% reduce 0%
17/06/09 10:32:30 INFO mapreduce.Job:  map 37% reduce 0%
17/06/09 10:32:31 INFO mapreduce.Job:  map 38% reduce 0%
17/06/09 10:32:34 INFO mapreduce.Job:  map 40% reduce 0%
17/06/09 10:32:36 INFO mapreduce.Job:  map 41% reduce 0%
17/06/09 10:32:37 INFO mapreduce.Job:  map 42% reduce 0%
17/06/09 10:32:38 INFO mapreduce.Job:  map 44% reduce 0%
17/06/09 10:32:43 INFO mapreduce.Job:  map 47% reduce 0%
17/06/09 10:32:44 INFO mapreduce.Job:  map 49% reduce 0%
17/06/09 10:32:45 INFO mapreduce.Job:  map 50% reduce 0%
17/06/09 10:32:48 INFO mapreduce.Job:  map 51% reduce 0%
17/06/09 10:32:50 INFO mapreduce.Job:  map 53% reduce 0%
17/06/09 10:32:53 INFO mapreduce.Job:  map 54% reduce 0%
17/06/09 10:32:54 INFO mapreduce.Job:  map 56% reduce 0%
17/06/09 10:32:55 INFO mapreduce.Job:  map 57% reduce 0%
17/06/09 10:32:56 INFO mapreduce.Job:  map 58% reduce 0%
17/06/09 10:32:57 INFO mapreduce.Job:  map 59% reduce 0%
17/06/09 10:32:58 INFO mapreduce.Job:  map 60% reduce 0%
17/06/09 10:33:02 INFO mapreduce.Job:  map 62% reduce 0%
17/06/09 10:33:04 INFO mapreduce.Job:  map 64% reduce 0%
17/06/09 10:33:06 INFO mapreduce.Job:  map 65% reduce 0%
17/06/09 10:33:07 INFO mapreduce.Job:  map 67% reduce 0%
17/06/09 10:33:08 INFO mapreduce.Job:  map 68% reduce 0%
17/06/09 10:33:11 INFO mapreduce.Job:  map 69% reduce 0%
17/06/09 10:33:13 INFO mapreduce.Job:  map 71% reduce 0%
17/06/09 10:33:14 INFO mapreduce.Job:  map 72% reduce 0%
17/06/09 10:33:15 INFO mapreduce.Job:  map 73% reduce 0%
17/06/09 10:33:16 INFO mapreduce.Job:  map 74% reduce 0%
17/06/09 10:33:19 INFO mapreduce.Job:  map 76% reduce 0%
17/06/09 10:33:20 INFO mapreduce.Job:  map 78% reduce 0%
17/06/09 10:33:24 INFO mapreduce.Job:  map 81% reduce 0%
17/06/09 10:33:25 INFO mapreduce.Job:  map 82% reduce 0%
17/06/09 10:33:27 INFO mapreduce.Job:  map 83% reduce 0%
17/06/09 10:33:32 INFO mapreduce.Job:  map 85% reduce 0%
17/06/09 10:33:33 INFO mapreduce.Job:  map 87% reduce 0%
17/06/09 10:33:35 INFO mapreduce.Job:  map 88% reduce 0%
17/06/09 10:33:36 INFO mapreduce.Job:  map 89% reduce 0%
17/06/09 10:33:43 INFO mapreduce.Job:  map 90% reduce 0%
17/06/09 10:33:44 INFO mapreduce.Job:  map 90% reduce 4%
17/06/09 10:33:45 INFO mapreduce.Job:  map 91% reduce 7%
17/06/09 10:33:47 INFO mapreduce.Job:  map 92% reduce 7%
17/06/09 10:33:48 INFO mapreduce.Job:  map 92% reduce 11%
17/06/09 10:33:49 INFO mapreduce.Job:  map 93% reduce 19%
17/06/09 10:33:52 INFO mapreduce.Job:  map 94% reduce 27%
17/06/09 10:33:54 INFO mapreduce.Job:  map 96% reduce 27%
17/06/09 10:33:56 INFO mapreduce.Job:  map 96% reduce 28%
17/06/09 10:33:59 INFO mapreduce.Job:  map 97% reduce 28%
17/06/09 10:34:00 INFO mapreduce.Job:  map 99% reduce 28%
17/06/09 10:34:03 INFO mapreduce.Job:  map 99% reduce 29%
17/06/09 10:34:04 INFO mapreduce.Job:  map 100% reduce 29%
17/06/09 10:34:06 INFO mapreduce.Job:  map 100% reduce 33%
17/06/09 10:34:07 INFO mapreduce.Job:  map 100% reduce 41%
17/06/09 10:34:08 INFO mapreduce.Job:  map 100% reduce 46%
17/06/09 10:34:09 INFO mapreduce.Job:  map 100% reduce 50%
17/06/09 10:34:10 INFO mapreduce.Job:  map 100% reduce 59%
17/06/09 10:34:12 INFO mapreduce.Job:  map 100% reduce 61%
17/06/09 10:34:13 INFO mapreduce.Job:  map 100% reduce 65%
17/06/09 10:34:14 INFO mapreduce.Job:  map 100% reduce 67%
17/06/09 10:34:15 INFO mapreduce.Job:  map 100% reduce 69%
17/06/09 10:34:16 INFO mapreduce.Job:  map 100% reduce 82%
17/06/09 10:34:18 INFO mapreduce.Job:  map 100% reduce 87%
17/06/09 10:34:19 INFO mapreduce.Job:  map 100% reduce 93%
17/06/09 10:34:20 INFO mapreduce.Job:  map 100% reduce 97%
17/06/09 10:34:22 INFO mapreduce.Job:  map 100% reduce 100%
17/06/09 10:34:24 INFO mapreduce.Job: Job job_1497003849298_0001 completed successfully
17/06/09 10:34:24 INFO mapreduce.Job: Counters: 49
        File System Counters
                FILE: Number of bytes read=2285253330
                FILE: Number of bytes written=4546215746
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=5120024180
                HDFS: Number of bytes written=5120000000
                HDFS: Number of read operations=492
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=16
        Job Counters
                Launched map tasks=156
                Launched reduce tasks=8
                Data-local map tasks=156
                Total time spent by all maps in occupied slots (ms)=1374553
                Total time spent by all reduces in occupied slots (ms)=356848
                Total time spent by all map tasks (ms)=1374553
                Total time spent by all reduce tasks (ms)=356848
                Total vcore-seconds taken by all map tasks=1374553
                Total vcore-seconds taken by all reduce tasks=356848
                Total megabyte-seconds taken by all map tasks=1407542272
                Total megabyte-seconds taken by all reduce tasks=365412352
        Map-Reduce Framework
                Map input records=51200000
                Map output records=51200000
                Map output bytes=5222400000
                Map output materialized bytes=2240098318
                Input split bytes=24180
                Combine input records=0
                Combine output records=0
                Reduce input groups=51200000
                Reduce shuffle bytes=2240098318
                Reduce input records=51200000
                Reduce output records=51200000
                Spilled Records=102400000
                Shuffled Maps =1248
                Failed Shuffles=0
                Merged Map outputs=1248
                GC time elapsed (ms)=28249
                CPU time spent (ms)=849090
                Physical memory (bytes) snapshot=80620503040
                Virtual memory (bytes) snapshot=454893223936
                Total committed heap usage (bytes)=81853939712
        Shuffle Errors
                BAD_ID=0
                CONNECTION=0
                IO_ERROR=0
                WRONG_LENGTH=0
                WRONG_MAP=0
                WRONG_REDUCE=0
        File Input Format Counters
                Bytes Read=5120000000
        File Output Format Counters
                Bytes Written=5120000000
17/06/09 10:34:24 INFO terasort.TeraSort: done

real    3m8.096s
user    0m10.151s
sys     0m1.099s
```