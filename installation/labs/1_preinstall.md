1. Check vm.swappiness on all your nodes
- First check and runtime change:
```
[root@ip-172-31-47-47 ~]# cat /proc/sys/vm/swappiness
60
[root@ip-172-31-47-47 ~]# sysctl vm.swappiness=1
[root@ip-172-31-47-47 ~]# cat /proc/sys/vm/swappiness
1
```
- Change it persistantly:
```
[root@ip-172-31-47-47 ~]# echo 'vm.swappiness = 1' >> /etc/sysctl.conf
```
2. Show the mount attributes of all volumes
- Mount data disk:
```
[root@ip-172-31-47-47 ~]# mkdir -p /data/01
[root@ip-172-31-47-47 ~]# mkfs -t ext4 /dev/xvdf
[root@ip-172-31-47-47 ~]# tune2fs -m 0 /dev/xvdf
[root@ip-172-31-47-47 ~]# mount /dev/xvdf /data/01
[root@ip-172-31-47-47 ~]# echo '/dev/xvdf /data/01 ext4 noatime 0 0' >> /etc/fstab
```
- Show attributes:
```
[root@ip-172-31-47-47 ~]# mount
/dev/xvde on / type ext4 (rw)
proc on /proc type proc (rw)
sysfs on /sys type sysfs (rw)
devpts on /dev/pts type devpts (rw,gid=5,mode=620)
tmpfs on /dev/shm type tmpfs (rw,rootcontext="system_u:object_r:tmpfs_t:s0")
none on /proc/sys/fs/binfmt_misc type binfmt_misc (rw)
/dev/xvdf on /data/01 type ext4 (rw)
```
3 - Show the reserve space of any non-root, ext-based volumes
```
[root@ip-172-31-47-47 ~]# tune2fs -l /dev/xvdf | grep Reserved
Reserved block count:     0
Reserved GDT blocks:      992
Reserved blocks uid:      0 (user root)
Reserved blocks gid:      0 (group root)
```
4 - Disable transparent hugepage support
- Transparent huges pages not found:
- Nevertheless, appended the following lines to /etc/rc.local
```
if test -f /sys/kernel/mm/transparent_hugepage/enabled; then
   echo never > /sys/kernel/mm/transparent_hugepage/enabled
fi
if test -f /sys/kernel/mm/transparent_hugepage/defrag; then
   echo never > /sys/kernel/mm/transparent_hugepage/defrag
fi
```
5 - List your network interface configuration
```
[root@ip-172-31-47-47 ~]# ip addr
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 16436 qdisc noqueue state UNKNOWN
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
    inet6 ::1/128 scope host
       valid_lft forever preferred_lft forever
2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 9001 qdisc pfifo_fast state UP qlen 1000
    link/ether 0a:8e:e3:83:bc:44 brd ff:ff:ff:ff:ff:ff
    inet 172.31.47.47/20 brd 172.31.47.255 scope global eth0
    inet6 fe80::88e:e3ff:fe83:bc44/64 scope link
       valid_lft forever preferred_lft forever
```
6 - List forward and reverse host lookups using getent or nslookup
- Reverse Lookup:
```
[root@ip-172-31-47-47 ~]# nslookup 172.31.47.47
Server:         172.31.0.2
Address:        172.31.0.2#53

Non-authoritative answer:
47.47.31.172.in-addr.arpa       name = ip-172-31-47-47.eu-west-1.compute.internal.

Authoritative answers can be found from:

```
- Lookup
```
[root@ip-172-31-47-47 ~]# nslookup ip-172-31-47-47.eu-west-1.compute.internal
Server:         172.31.0.2
Address:        172.31.0.2#53

Non-authoritative answer:
Name:   ip-172-31-47-47.eu-west-1.compute.internal
Address: 172.31.47.47
```
7 - Show the nscd service is running
```
[root@ip-172-31-47-47 ~]# service nscd start
Starting nscd:                                             [  OK  ]
[root@ip-172-31-47-47 ~]# service nscd status
nscd (pid 1578) is running...
```
8 - Show the ntpd service is running
```
[root@ip-172-31-47-47 ~]# service ntpd start
Starting ntpd:                                             [  OK  ]
[root@ip-172-31-47-47 ~]# service ntpd status
ntpd (pid  1670) is running...
```