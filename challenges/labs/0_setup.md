- List the cloud provider you are using (AWS, GCE, Azure, other)
```
AWS
```
- List the Linux release you have chosen
```
CentOS 6.4
```
- Show that the disk space on each node is at least 30 GB
```
[root@ip-172-31-24-220 ~]# df -h
Filesystem            Size  Used Avail Use% Mounted on
/dev/xvde              50G  721M   47G   2% /
tmpfs                 7.4G     0  7.4G   0% /dev/shm


[root@ip-172-31-19-203 ~]# df -h
Filesystem            Size  Used Avail Use% Mounted on
/dev/xvde              50G  721M   47G   2% /
tmpfs                 7.4G     0  7.4G   0% /dev/shm


[root@ip-172-31-16-137 ~]# df -h
Filesystem            Size  Used Avail Use% Mounted on
/dev/xvde              50G  721M   47G   2% /
tmpfs                 7.4G     0  7.4G   0% /dev/shm

[root@ip-172-31-17-217 ~]# df -h
Filesystem            Size  Used Avail Use% Mounted on
/dev/xvde              50G  721M   47G   2% /
tmpfs                 7.4G     0  7.4G   0% /dev/shm

[root@ip-172-31-19-96 ~]# df -h
Filesystem            Size  Used Avail Use% Mounted on
/dev/xvde              50G  721M   47G   2% /
tmpfs                 7.4G     0  7.4G   0% /dev/shm

```
- List the command and output for yum repolist enabled
```
[root@ip-172-31-24-220 ~]# yum repolist enabled
Loaded plugins: fastestmirror, presto
Determining fastest mirrors
 * base: mirrors.coreix.net
 * extras: centos.mirroring.pulsant.co.uk
 * updates: centos.mirroring.pulsant.co.uk
repo id                                                          repo name                                                                    status
base                                                             CentOS-6 - Base                                                              6,706
extras                                                           CentOS-6 - Extras                                                               45
updates                                                          CentOS-6 - Updates                                                             354
repolist: 7,105
```
- Create user and groups
```
[root@ip-172-31-19-96 ~]# sudo groupadd conservative
[root@ip-172-31-19-96 ~]# sudo groupadd labour
[root@ip-172-31-19-96 ~]# sudo useradd -u 2000 -g conservative theresa
[root@ip-172-31-19-96 ~]# sudo useradd -u 3000 -g labour jeremy
```
- List the /etc/passwd entries for theresa and jeremy in your setup file
```
[root@ip-172-31-19-96 ~]# cat /etc/passwd | grep "theresa\|jeremy"
theresa:x:2000:500::/home/theresa:/bin/bash
jeremy:x:3000:501::/home/jeremy:/bin/bash
```
- List the /etc/group entries for conservative and labour in your setup file
```
[root@ip-172-31-19-96 ~]# cat /etc/group | grep "conservative\|labour"
conservative:x:500:
labour:x:501:
```