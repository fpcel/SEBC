- Source Directory:
```
[root@ip-172-31-47-47 ~]# hdfs fsck /fpcel -files -blocks
Connecting to namenode via http://ip-172-31-34-16.eu-west-1.compute.internal:50070
FSCK started by root (auth:SIMPLE) from /172.31.47.47 for path /fpcel at Tue Jun 06 14:23:00 UTC 2017
/fpcel <dir>
/fpcel/teragen-output <dir>
/fpcel/teragen-output/_SUCCESS 0 bytes, 0 block(s):  OK

/fpcel/teragen-output/part-m-00000 256000000 bytes, 2 block(s):  OK
0. BP-872602494-172.31.34.16-1496749930643:blk_1073742626_1802 len=134217728 Live_repl=3
1. BP-872602494-172.31.34.16-1496749930643:blk_1073742628_1804 len=121782272 Live_repl=3

/fpcel/teragen-output/part-m-00001 256000000 bytes, 2 block(s):  OK
0. BP-872602494-172.31.34.16-1496749930643:blk_1073742627_1803 len=134217728 Live_repl=3
1. BP-872602494-172.31.34.16-1496749930643:blk_1073742629_1805 len=121782272 Live_repl=3

Status: HEALTHY
 Total size:    512000000 B
 Total dirs:    2
 Total files:   3
 Total symlinks:                0
 Total blocks (validated):      4 (avg. block size 128000000 B)
 Minimally replicated blocks:   4 (100.0 %)
 Over-replicated blocks:        0 (0.0 %)
 Under-replicated blocks:       0 (0.0 %)
 Mis-replicated blocks:         0 (0.0 %)
 Default replication factor:    3
 Average block replication:     3.0
 Corrupt blocks:                0
 Missing replicas:              0 (0.0 %)
 Number of data-nodes:          3
 Number of racks:               1
FSCK ended at Tue Jun 06 14:23:00 UTC 2017 in 2 milliseconds


The filesystem under path '/fpcel' is HEALTHY

```
- Target Directory:
```
[root@ip-172-31-47-47 ~]# hdfs fsck /cmeralto -files -blocks
Connecting to namenode via http://ip-172-31-34-16.eu-west-1.compute.internal:50070
FSCK started by root (auth:SIMPLE) from /172.31.47.47 for path /cmeralto at Tue Jun 06 14:24:37 UTC 2017
/cmeralto <dir>
/cmeralto/teragen-output <dir>
/cmeralto/teragen-output/_SUCCESS 0 bytes, 0 block(s):  OK

/cmeralto/teragen-output/part-m-00000 256000000 bytes, 2 block(s):  OK
0. BP-872602494-172.31.34.16-1496749930643:blk_1073742756_1932 len=134217728 Live_repl=3
1. BP-872602494-172.31.34.16-1496749930643:blk_1073742759_1935 len=121782272 Live_repl=3

/cmeralto/teragen-output/part-m-00001 256000000 bytes, 2 block(s):  OK
0. BP-872602494-172.31.34.16-1496749930643:blk_1073742758_1934 len=134217728 Live_repl=3
1. BP-872602494-172.31.34.16-1496749930643:blk_1073742760_1936 len=121782272 Live_repl=3

Status: HEALTHY
 Total size:    512000000 B
 Total dirs:    2
 Total files:   3
 Total symlinks:                0
 Total blocks (validated):      4 (avg. block size 128000000 B)
 Minimally replicated blocks:   4 (100.0 %)
 Over-replicated blocks:        0 (0.0 %)
 Under-replicated blocks:       0 (0.0 %)
 Mis-replicated blocks:         0 (0.0 %)
 Default replication factor:    3
 Average block replication:     3.0
 Corrupt blocks:                0
 Missing replicas:              0 (0.0 %)
 Number of data-nodes:          3
 Number of racks:               1
FSCK ended at Tue Jun 06 14:24:37 UTC 2017 in 2 milliseconds


The filesystem under path '/cmeralto' is HEALTHY

```