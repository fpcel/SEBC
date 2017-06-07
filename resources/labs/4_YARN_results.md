- Slowest Run (1GB test)
```
-------------------------------------------
Running test with:
    -Dmapreduce.job.maps=8
    -Dmapreduce.job.reduces=1
    -Dmapreduce.map.memory.mb=1024
    -Dmapreduce.map.java.opts.max.heap=819
    -Dmapreduce.reduce.memory.mb=1024
    -Dmapreduce.reduce.java.opts.max.heap=819
Teragen time:

real    0m30.813s
user    0m5.905s
sys     0m0.675s
Terasort time:

real    1m4.143s
user    0m7.670s
sys     0m0.735s
Deleted /results/tg-1GB-8-1-1024
Deleted /results/ts-1GB-8-1-1024
```
- Fastest Run (1GB test)
```
Running test with:
    -Dmapreduce.job.maps=2
    -Dmapreduce.job.reduces=2
    -Dmapreduce.map.memory.mb=1024
    -Dmapreduce.map.java.opts.max.heap=819
    -Dmapreduce.reduce.memory.mb=1024
    -Dmapreduce.reduce.java.opts.max.heap=819
Teragen time:

real    0m23.549s
user    0m5.775s
sys     0m0.641s
Terasort time:

real    0m50.019s
user    0m7.375s
sys     0m0.730s
Deleted /results/tg-1GB-2-2-1024
Deleted /results/ts-1GB-2-2-1024
```