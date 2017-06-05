1. Check vm.swappiness on all your nodes
- First check:
```
> cat /proc/sys/vm/swappiness
60
> sysctl vm.swappiness=1
> cat /proc/sys/vm/swappiness
1
```
- Change it persistantly:
```
echo 'vm.swappiness = 1' >> /etc/sysctl.conf
```
