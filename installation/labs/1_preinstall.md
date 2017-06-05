1. Check vm.swappiness on all your nodes
- First check:
<code>
cat /proc/sys/vm/swappiness
</code>
60
- Change it at runtime:
<code>
sysctl vm.swappiness=1
</code>
- Change it persistantly:
<code>
echo 'vm.swappiness = 1' >> /etc/sysctl.conf
</code>
- Final check:
<code>
cat /proc/sys/vm/swappiness
</code>
1