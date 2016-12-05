=======================================================================================================================================================
1. 	Check vm.swappiness on all your nodes	(change for all nodes)
	Set the value to 1 if necessary
=======================================================================================================================================================

[centos@ip-172-31-5-137 ~]$ sudo vi /etc/sysctl.conf
[centos@ip-172-31-5-137 ~]$ sudo cat /etc/sysctl.conf|grep swap
vm.swappiness=1
[centos@ip-172-31-5-137 ~]$ sudo sysctl -p
vm.swappiness = 1

[centos@ip-172-31-5-138 ~]$ sudo vi /etc/sysctl.conf
[centos@ip-172-31-5-138 ~]$ sudo cat /etc/sysctl.conf|grep swap
vm.swappiness=1
[centos@ip-172-31-5-138 ~]$ sudo sysctl -p
vm.swappiness = 1

[centos@ip-172-31-5-139 ~]$ sudo vi /etc/sysctl.conf
[centos@ip-172-31-5-139 ~]$ sudo cat /etc/sysctl.conf|grep swap
vm.swappiness=1
[centos@ip-172-31-5-139 ~]$ sudo sysctl -p
vm.swappiness = 1

[centos@ip-172-31-5-140 ~]$ sudo vi /etc/sysctl.conf
[centos@ip-172-31-5-140 ~]$ sudo cat /etc/sysctl.conf|grep swap
vm.swappiness=1
[centos@ip-172-31-5-140 ~]$ sudo sysctl -p
vm.swappiness = 1

[centos@ip-172-31-5-141 ~]$ sudo vi /etc/sysctl.conf
[centos@ip-172-31-5-141 ~]$ sudo cat /etc/sysctl.conf|grep swap
vm.swappiness=1
[centos@ip-172-31-5-141 ~]$ sudo sysctl -p
vm.swappiness = 1


=======================================================================================================================================================
2.	Show the mount attributes of all volumes (same for all nodes)
=======================================================================================================================================================

[centos@ip-172-31-5-137 ~]$ mount
sysfs on /sys type sysfs (rw,nosuid,nodev,noexec,relatime,seclabel)
proc on /proc type proc (rw,nosuid,nodev,noexec,relatime)
devtmpfs on /dev type devtmpfs (rw,nosuid,seclabel,size=7599028k,nr_inodes=1899757,mode=755)
securityfs on /sys/kernel/security type securityfs (rw,nosuid,nodev,noexec,relatime)
tmpfs on /dev/shm type tmpfs (rw,nosuid,nodev,seclabel)
devpts on /dev/pts type devpts (rw,nosuid,noexec,relatime,seclabel,gid=5,mode=620,ptmxmode=000)
tmpfs on /run type tmpfs (rw,nosuid,nodev,seclabel,mode=755)
tmpfs on /sys/fs/cgroup type tmpfs (ro,nosuid,nodev,noexec,seclabel,mode=755)
cgroup on /sys/fs/cgroup/systemd type cgroup (rw,nosuid,nodev,noexec,relatime,xattr,release_agent=/usr/lib/systemd/systemd-cgroups-agent,name=systemd)
pstore on /sys/fs/pstore type pstore (rw,nosuid,nodev,noexec,relatime)
cgroup on /sys/fs/cgroup/cpu,cpuacct type cgroup (rw,nosuid,nodev,noexec,relatime,cpuacct,cpu)
cgroup on /sys/fs/cgroup/devices type cgroup (rw,nosuid,nodev,noexec,relatime,devices)
cgroup on /sys/fs/cgroup/freezer type cgroup (rw,nosuid,nodev,noexec,relatime,freezer)
cgroup on /sys/fs/cgroup/perf_event type cgroup (rw,nosuid,nodev,noexec,relatime,perf_event)
cgroup on /sys/fs/cgroup/hugetlb type cgroup (rw,nosuid,nodev,noexec,relatime,hugetlb)
cgroup on /sys/fs/cgroup/memory type cgroup (rw,nosuid,nodev,noexec,relatime,memory)
cgroup on /sys/fs/cgroup/cpuset type cgroup (rw,nosuid,nodev,noexec,relatime,cpuset)
cgroup on /sys/fs/cgroup/blkio type cgroup (rw,nosuid,nodev,noexec,relatime,blkio)
cgroup on /sys/fs/cgroup/net_cls type cgroup (rw,nosuid,nodev,noexec,relatime,net_cls)
configfs on /sys/kernel/config type configfs (rw,relatime)
/dev/xvda1 on / type xfs (rw,relatime,seclabel,attr2,inode64,noquota)
rpc_pipefs on /var/lib/nfs/rpc_pipefs type rpc_pipefs (rw,relatime)
selinuxfs on /sys/fs/selinux type selinuxfs (rw,relatime)
systemd-1 on /proc/sys/fs/binfmt_misc type autofs (rw,relatime,fd=31,pgrp=1,timeout=300,minproto=5,maxproto=5,direct)
debugfs on /sys/kernel/debug type debugfs (rw,relatime)
hugetlbfs on /dev/hugepages type hugetlbfs (rw,relatime,seclabel)
mqueue on /dev/mqueue type mqueue (rw,relatime,seclabel)
nfsd on /proc/fs/nfsd type nfsd (rw,relatime)
tmpfs on /run/user/1000 type tmpfs (rw,nosuid,nodev,relatime,seclabel,size=1497312k,mode=700,uid=1000,gid=1000)


[centos@ip-172-31-5-138 ~]$ mount
sysfs on /sys type sysfs (rw,nosuid,nodev,noexec,relatime,seclabel)
proc on /proc type proc (rw,nosuid,nodev,noexec,relatime)
devtmpfs on /dev type devtmpfs (rw,nosuid,seclabel,size=7599028k,nr_inodes=1899757,mode=755)
securityfs on /sys/kernel/security type securityfs (rw,nosuid,nodev,noexec,relatime)
tmpfs on /dev/shm type tmpfs (rw,nosuid,nodev,seclabel)
devpts on /dev/pts type devpts (rw,nosuid,noexec,relatime,seclabel,gid=5,mode=620,ptmxmode=000)
tmpfs on /run type tmpfs (rw,nosuid,nodev,seclabel,mode=755)
tmpfs on /sys/fs/cgroup type tmpfs (ro,nosuid,nodev,noexec,seclabel,mode=755)
cgroup on /sys/fs/cgroup/systemd type cgroup (rw,nosuid,nodev,noexec,relatime,xattr,release_agent=/usr/lib/systemd/systemd-cgroups-agent,name=systemd)
pstore on /sys/fs/pstore type pstore (rw,nosuid,nodev,noexec,relatime)
cgroup on /sys/fs/cgroup/blkio type cgroup (rw,nosuid,nodev,noexec,relatime,blkio)
cgroup on /sys/fs/cgroup/cpu,cpuacct type cgroup (rw,nosuid,nodev,noexec,relatime,cpuacct,cpu)
cgroup on /sys/fs/cgroup/cpuset type cgroup (rw,nosuid,nodev,noexec,relatime,cpuset)
cgroup on /sys/fs/cgroup/net_cls type cgroup (rw,nosuid,nodev,noexec,relatime,net_cls)
cgroup on /sys/fs/cgroup/hugetlb type cgroup (rw,nosuid,nodev,noexec,relatime,hugetlb)
cgroup on /sys/fs/cgroup/devices type cgroup (rw,nosuid,nodev,noexec,relatime,devices)
cgroup on /sys/fs/cgroup/freezer type cgroup (rw,nosuid,nodev,noexec,relatime,freezer)
cgroup on /sys/fs/cgroup/perf_event type cgroup (rw,nosuid,nodev,noexec,relatime,perf_event)
cgroup on /sys/fs/cgroup/memory type cgroup (rw,nosuid,nodev,noexec,relatime,memory)
configfs on /sys/kernel/config type configfs (rw,relatime)
/dev/xvda1 on / type xfs (rw,relatime,seclabel,attr2,inode64,noquota)
rpc_pipefs on /var/lib/nfs/rpc_pipefs type rpc_pipefs (rw,relatime)
selinuxfs on /sys/fs/selinux type selinuxfs (rw,relatime)
systemd-1 on /proc/sys/fs/binfmt_misc type autofs (rw,relatime,fd=27,pgrp=1,timeout=300,minproto=5,maxproto=5,direct)
mqueue on /dev/mqueue type mqueue (rw,relatime,seclabel)
hugetlbfs on /dev/hugepages type hugetlbfs (rw,relatime,seclabel)
debugfs on /sys/kernel/debug type debugfs (rw,relatime)
nfsd on /proc/fs/nfsd type nfsd (rw,relatime)
tmpfs on /run/user/1000 type tmpfs (rw,nosuid,nodev,relatime,seclabel,size=1497312k,mode=700,uid=1000,gid=1000)


[centos@ip-172-31-5-139 ~]$ mount
sysfs on /sys type sysfs (rw,nosuid,nodev,noexec,relatime,seclabel)
proc on /proc type proc (rw,nosuid,nodev,noexec,relatime)
devtmpfs on /dev type devtmpfs (rw,nosuid,seclabel,size=7599028k,nr_inodes=1899757,mode=755)
securityfs on /sys/kernel/security type securityfs (rw,nosuid,nodev,noexec,relatime)
tmpfs on /dev/shm type tmpfs (rw,nosuid,nodev,seclabel)
devpts on /dev/pts type devpts (rw,nosuid,noexec,relatime,seclabel,gid=5,mode=620,ptmxmode=000)
tmpfs on /run type tmpfs (rw,nosuid,nodev,seclabel,mode=755)
tmpfs on /sys/fs/cgroup type tmpfs (ro,nosuid,nodev,noexec,seclabel,mode=755)
cgroup on /sys/fs/cgroup/systemd type cgroup (rw,nosuid,nodev,noexec,relatime,xattr,release_agent=/usr/lib/systemd/systemd-cgroups-agent,name=systemd)
pstore on /sys/fs/pstore type pstore (rw,nosuid,nodev,noexec,relatime)
cgroup on /sys/fs/cgroup/cpuset type cgroup (rw,nosuid,nodev,noexec,relatime,cpuset)
cgroup on /sys/fs/cgroup/memory type cgroup (rw,nosuid,nodev,noexec,relatime,memory)
cgroup on /sys/fs/cgroup/blkio type cgroup (rw,nosuid,nodev,noexec,relatime,blkio)
cgroup on /sys/fs/cgroup/devices type cgroup (rw,nosuid,nodev,noexec,relatime,devices)
cgroup on /sys/fs/cgroup/freezer type cgroup (rw,nosuid,nodev,noexec,relatime,freezer)
cgroup on /sys/fs/cgroup/perf_event type cgroup (rw,nosuid,nodev,noexec,relatime,perf_event)
cgroup on /sys/fs/cgroup/cpu,cpuacct type cgroup (rw,nosuid,nodev,noexec,relatime,cpuacct,cpu)
cgroup on /sys/fs/cgroup/net_cls type cgroup (rw,nosuid,nodev,noexec,relatime,net_cls)
cgroup on /sys/fs/cgroup/hugetlb type cgroup (rw,nosuid,nodev,noexec,relatime,hugetlb)
configfs on /sys/kernel/config type configfs (rw,relatime)
/dev/xvda1 on / type xfs (rw,relatime,seclabel,attr2,inode64,noquota)
rpc_pipefs on /var/lib/nfs/rpc_pipefs type rpc_pipefs (rw,relatime)
selinuxfs on /sys/fs/selinux type selinuxfs (rw,relatime)
systemd-1 on /proc/sys/fs/binfmt_misc type autofs (rw,relatime,fd=27,pgrp=1,timeout=300,minproto=5,maxproto=5,direct)
debugfs on /sys/kernel/debug type debugfs (rw,relatime)
hugetlbfs on /dev/hugepages type hugetlbfs (rw,relatime,seclabel)
mqueue on /dev/mqueue type mqueue (rw,relatime,seclabel)
nfsd on /proc/fs/nfsd type nfsd (rw,relatime)
tmpfs on /run/user/1000 type tmpfs (rw,nosuid,nodev,relatime,seclabel,size=1497312k,mode=700,uid=1000,gid=1000)


[centos@ip-172-31-5-140 ~]$ mount
sysfs on /sys type sysfs (rw,nosuid,nodev,noexec,relatime,seclabel)
proc on /proc type proc (rw,nosuid,nodev,noexec,relatime)
devtmpfs on /dev type devtmpfs (rw,nosuid,seclabel,size=7599028k,nr_inodes=1899757,mode=755)
securityfs on /sys/kernel/security type securityfs (rw,nosuid,nodev,noexec,relatime)
tmpfs on /dev/shm type tmpfs (rw,nosuid,nodev,seclabel)
devpts on /dev/pts type devpts (rw,nosuid,noexec,relatime,seclabel,gid=5,mode=620,ptmxmode=000)
tmpfs on /run type tmpfs (rw,nosuid,nodev,seclabel,mode=755)
tmpfs on /sys/fs/cgroup type tmpfs (ro,nosuid,nodev,noexec,seclabel,mode=755)
cgroup on /sys/fs/cgroup/systemd type cgroup (rw,nosuid,nodev,noexec,relatime,xattr,release_agent=/usr/lib/systemd/systemd-cgroups-agent,name=systemd)
pstore on /sys/fs/pstore type pstore (rw,nosuid,nodev,noexec,relatime)
cgroup on /sys/fs/cgroup/cpu,cpuacct type cgroup (rw,nosuid,nodev,noexec,relatime,cpuacct,cpu)
cgroup on /sys/fs/cgroup/hugetlb type cgroup (rw,nosuid,nodev,noexec,relatime,hugetlb)
cgroup on /sys/fs/cgroup/net_cls type cgroup (rw,nosuid,nodev,noexec,relatime,net_cls)
cgroup on /sys/fs/cgroup/devices type cgroup (rw,nosuid,nodev,noexec,relatime,devices)
cgroup on /sys/fs/cgroup/perf_event type cgroup (rw,nosuid,nodev,noexec,relatime,perf_event)
cgroup on /sys/fs/cgroup/freezer type cgroup (rw,nosuid,nodev,noexec,relatime,freezer)
cgroup on /sys/fs/cgroup/cpuset type cgroup (rw,nosuid,nodev,noexec,relatime,cpuset)
cgroup on /sys/fs/cgroup/blkio type cgroup (rw,nosuid,nodev,noexec,relatime,blkio)
cgroup on /sys/fs/cgroup/memory type cgroup (rw,nosuid,nodev,noexec,relatime,memory)
configfs on /sys/kernel/config type configfs (rw,relatime)
/dev/xvda1 on / type xfs (rw,relatime,seclabel,attr2,inode64,noquota)
rpc_pipefs on /var/lib/nfs/rpc_pipefs type rpc_pipefs (rw,relatime)
selinuxfs on /sys/fs/selinux type selinuxfs (rw,relatime)
systemd-1 on /proc/sys/fs/binfmt_misc type autofs (rw,relatime,fd=28,pgrp=1,timeout=300,minproto=5,maxproto=5,direct)
debugfs on /sys/kernel/debug type debugfs (rw,relatime)
hugetlbfs on /dev/hugepages type hugetlbfs (rw,relatime,seclabel)
mqueue on /dev/mqueue type mqueue (rw,relatime,seclabel)
nfsd on /proc/fs/nfsd type nfsd (rw,relatime)
tmpfs on /run/user/1000 type tmpfs (rw,nosuid,nodev,relatime,seclabel,size=1497312k,mode=700,uid=1000,gid=1000)



[centos@ip-172-31-5-141 ~]$ mount
sysfs on /sys type sysfs (rw,nosuid,nodev,noexec,relatime,seclabel)
proc on /proc type proc (rw,nosuid,nodev,noexec,relatime)
devtmpfs on /dev type devtmpfs (rw,nosuid,seclabel,size=7599028k,nr_inodes=1899757,mode=755)
securityfs on /sys/kernel/security type securityfs (rw,nosuid,nodev,noexec,relatime)
tmpfs on /dev/shm type tmpfs (rw,nosuid,nodev,seclabel)
devpts on /dev/pts type devpts (rw,nosuid,noexec,relatime,seclabel,gid=5,mode=620,ptmxmode=000)
tmpfs on /run type tmpfs (rw,nosuid,nodev,seclabel,mode=755)
tmpfs on /sys/fs/cgroup type tmpfs (ro,nosuid,nodev,noexec,seclabel,mode=755)
cgroup on /sys/fs/cgroup/systemd type cgroup (rw,nosuid,nodev,noexec,relatime,xattr,release_agent=/usr/lib/systemd/systemd-cgroups-agent,name=systemd)
pstore on /sys/fs/pstore type pstore (rw,nosuid,nodev,noexec,relatime)
cgroup on /sys/fs/cgroup/devices type cgroup (rw,nosuid,nodev,noexec,relatime,devices)
cgroup on /sys/fs/cgroup/perf_event type cgroup (rw,nosuid,nodev,noexec,relatime,perf_event)
cgroup on /sys/fs/cgroup/hugetlb type cgroup (rw,nosuid,nodev,noexec,relatime,hugetlb)
cgroup on /sys/fs/cgroup/cpu,cpuacct type cgroup (rw,nosuid,nodev,noexec,relatime,cpuacct,cpu)
cgroup on /sys/fs/cgroup/memory type cgroup (rw,nosuid,nodev,noexec,relatime,memory)
cgroup on /sys/fs/cgroup/net_cls type cgroup (rw,nosuid,nodev,noexec,relatime,net_cls)
cgroup on /sys/fs/cgroup/cpuset type cgroup (rw,nosuid,nodev,noexec,relatime,cpuset)
cgroup on /sys/fs/cgroup/freezer type cgroup (rw,nosuid,nodev,noexec,relatime,freezer)
cgroup on /sys/fs/cgroup/blkio type cgroup (rw,nosuid,nodev,noexec,relatime,blkio)
configfs on /sys/kernel/config type configfs (rw,relatime)
/dev/xvda1 on / type xfs (rw,relatime,seclabel,attr2,inode64,noquota)
rpc_pipefs on /var/lib/nfs/rpc_pipefs type rpc_pipefs (rw,relatime)
selinuxfs on /sys/fs/selinux type selinuxfs (rw,relatime)
systemd-1 on /proc/sys/fs/binfmt_misc type autofs (rw,relatime,fd=31,pgrp=1,timeout=300,minproto=5,maxproto=5,direct)
mqueue on /dev/mqueue type mqueue (rw,relatime,seclabel)
hugetlbfs on /dev/hugepages type hugetlbfs (rw,relatime,seclabel)
debugfs on /sys/kernel/debug type debugfs (rw,relatime)
nfsd on /proc/fs/nfsd type nfsd (rw,relatime)
tmpfs on /run/user/1000 type tmpfs (rw,nosuid,nodev,relatime,seclabel,size=1497312k,mode=700,uid=1000,gid=1000)
[centos@ip-172-31-5-141 ~]$


=======================================================================================================================================================
3.	Show the reserve space of any non-root, ext-based volumes (same for all nodes)
=======================================================================================================================================================
[centos@ip-172-31-5-140 ~]$ df -h
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda1       30G  877M   30G   3% /
devtmpfs        7.3G     0  7.3G   0% /dev
tmpfs           7.2G     0  7.2G   0% /dev/shm
tmpfs           7.2G   17M  7.2G   1% /run
tmpfs           7.2G     0  7.2G   0% /sys/fs/cgroup
tmpfs           1.5G     0  1.5G   0% /run/user/0
tmpfs           1.5G     0  1.5G   0% /run/user/1000


=======================================================================================================================================================
4.	Show that transparent hugepages is disabled (same for all nodes)
=======================================================================================================================================================
sudo vi /etc/rc.d/rc.local
if test -f /sys/kernel/mm/transparent_hugepage/enabled; then
echo never > /sys/kernel/mm/transparent_hugepage/enabled
fi
if test -f /sys/kernel/mm/transparent_hugepage/defrag; then
echo never > /sys/kernel/mm/transparent_hugepage/defrag
fi
sudo chmod u+x /etc/rc.d/rc.local
sudo init 6

[centos@ip-172-31-5-137 ~]$ cat /sys/kernel/mm/transparent_hugepage/enabled; cat /sys/kernel/mm/transparent_hugepage/defrag
always madvise [never]
always madvise [never]

[centos@ip-172-31-5-138 ~]$ cat /sys/kernel/mm/transparent_hugepage/enabled; cat /sys/kernel/mm/transparent_hugepage/defrag
always madvise [never]
always madvise [never]

[centos@ip-172-31-5-139 ~]$ cat /sys/kernel/mm/transparent_hugepage/enabled; cat /sys/kernel/mm/transparent_hugepage/defrag
always madvise [never]
always madvise [never]

[centos@ip-172-31-5-140 ~]$ cat /sys/kernel/mm/transparent_hugepage/enabled; cat /sys/kernel/mm/transparent_hugepage/defrag
always madvise [never]
always madvise [never]

[centos@ip-172-31-5-141 ~]$ cat /sys/kernel/mm/transparent_hugepage/enabled; cat /sys/kernel/mm/transparent_hugepage/defrag
always madvise [never]
always madvise [never]


=======================================================================================================================================================
5.	Report the network interface attributes
=======================================================================================================================================================

[centos@ip-172-31-5-137 ~]$ ip link show
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN mode DEFAULT
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 9001 qdisc pfifo_fast state UP mode DEFAULT qlen 1000
    link/ether 02:f4:05:f6:55:13 brd ff:ff:ff:ff:ff:ff


[centos@ip-172-31-5-138 ~]$ ip link show
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN mode DEFAULT
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 9001 qdisc pfifo_fast state UP mode DEFAULT qlen 1000
    link/ether 02:62:2f:e7:a9:7b brd ff:ff:ff:ff:ff:ff


[centos@ip-172-31-5-139 ~]$ ip link show
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN mode DEFAULT
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 9001 qdisc pfifo_fast state UP mode DEFAULT qlen 1000
    link/ether 02:15:d6:5e:d1:ed brd ff:ff:ff:ff:ff:ff


[centos@ip-172-31-5-140 ~]$ ip link show
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN mode DEFAULT
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 9001 qdisc pfifo_fast state UP mode DEFAULT qlen 1000
    link/ether 02:53:47:43:35:eb brd ff:ff:ff:ff:ff:ff


[centos@ip-172-31-5-141 ~]$ ip link show
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN mode DEFAULT
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 9001 qdisc pfifo_fast state UP mode DEFAULT qlen 1000
    link/ether 02:a5:25:6b:5f:61 brd ff:ff:ff:ff:ff:ff


=======================================================================================================================================================
6.	Show forward and reverse host lookups using getent and nslookup (all nodes checked)
=======================================================================================================================================================
-----------------------------------------------------------------------------------------------------------------------------------------------------
getent
-----------------------------------------------------------------------------------------------------------------------------------------------------
[centos@ip-172-31-5-137 ~]$ getent hosts ip-172-31-5-137.ap-southeast-1.compute.internal
172.31.5.137    ip-172-31-5-137.ap-southeast-1.compute.internal
[centos@ip-172-31-5-137 ~]$ 
[centos@ip-172-31-5-137 ~]$ nslookup ip-172-31-5-137.ap-southeast-1.compute.internal
Server:         172.31.0.2
Address:        172.31.0.2#53

Non-authoritative answer:
Name:   ip-172-31-5-137.ap-southeast-1.compute.internal
Address: 172.31.5.137


[centos@ip-172-31-5-138 ~]$ getent hosts ip-172-31-5-138.ap-southeast-1.compute.internal
172.31.5.138    ip-172-31-5-138.ap-southeast-1.compute.internal
[centos@ip-172-31-5-138 ~]$
[centos@ip-172-31-5-138 ~]$ nslookup ip-172-31-5-138.ap-southeast-1.compute.internal
Server:         172.31.0.2
Address:        172.31.0.2#53

Non-authoritative answer:
Name:   ip-172-31-5-138.ap-southeast-1.compute.internal
Address: 172.31.5.138


[centos@ip-172-31-5-139 ~]$ getent hosts ip-172-31-5-139.ap-southeast-1.compute.internal
172.31.5.139    ip-172-31-5-139.ap-southeast-1.compute.internal
[centos@ip-172-31-5-139 ~]$
[centos@ip-172-31-5-139 ~]$ nslookup
> ^C[centos@ip-172-31-5-139 ~]$ nslookup ip-172-31-5-139.ap-southeast-1.compute.internal
Server:         172.31.0.2
Address:        172.31.0.2#53

Non-authoritative answer:
Name:   ip-172-31-5-139.ap-southeast-1.compute.internal
Address: 172.31.5.139


[centos@ip-172-31-5-140 ~]$ getent hosts ip-172-31-5-140.ap-southeast-1.compute.internal
172.31.5.140    ip-172-31-5-140.ap-southeast-1.compute.internal
[centos@ip-172-31-5-140 ~]$
[centos@ip-172-31-5-140 ~]$ nslookup ip-172-31-5-140.ap-southeast-1.compute.internal
Server:         172.31.0.2
Address:        172.31.0.2#53

Non-authoritative answer:
Name:   ip-172-31-5-140.ap-southeast-1.compute.internal
Address: 172.31.5.140


[centos@ip-172-31-5-141 ~]$ getent hosts ip-172-31-5-141.ap-southeast-1.compute.internal
172.31.5.141    ip-172-31-5-141.ap-southeast-1.compute.internal
[centos@ip-172-31-5-141 ~]$
[centos@ip-172-31-5-141 ~]$ nslookup ip-172-31-5-141.ap-southeast-1.compute.internal
Server:         172.31.0.2
Address:        172.31.0.2#53

Non-authoritative answer:
Name:   ip-172-31-5-141.ap-southeast-1.compute.internal
Address: 172.31.5.141


=======================================================================================================================================================
7.	Verify the nscd service is running (same for all nodes)
=======================================================================================================================================================

sudo yum install -y nscd
sudo mkdir /var/db/nscd 
sudo touch /var/db/netgroup
sudo service nscd start

[centos@ip-172-31-5-137 ~]$ systemctl list-units --type service|grep nscd
nscd.service                       loaded active running Name Service Cache Daemon

[centos@ip-172-31-5-138 ~]$ systemctl list-units --type service|grep nscd
nscd.service                       loaded active running Name Service Cache Daemon

[centos@ip-172-31-5-139 ~]$ systemctl list-units --type service|grep nscd
nscd.service                       loaded active running Name Service Cache Daemon

[centos@ip-172-31-5-140 ~]$ systemctl list-units --type service|grep nscd
nscd.service                       loaded active running Name Service Cache Daemon

[centos@ip-172-31-5-141 ~]$ systemctl list-units --type service|grep nscd
nscd.service                       loaded active running Name Service Cache Daemon


=======================================================================================================================================================
8.	Verify the ntpd service is running (same for all nodes)
=======================================================================================================================================================

nodes must be able to ping each other

sudo yum install -y ntpd
sudo systemctl enable ntpd
sudo systemctl start ntpd
ntpq -p 
ntpstat 
sudo systemctl stop ntpd
sudo systemctl start ntpd

[centos@ip-172-31-5-137 ~]$ systemctl list-units --type service|grep ntpd
ntpd.service                       loaded active running Network Time Service

[centos@ip-172-31-5-138 ~]$  systemctl list-units --type service|grep ntpd
ntpd.service                       loaded active running Network Time Service

[centos@ip-172-31-5-139 ~]$  systemctl list-units --type service|grep ntpd
ntpd.service                       loaded active running Network Time Service

[centos@ip-172-31-5-140 ~]$  systemctl list-units --type service|grep ntpd
ntpd.service                       loaded active running Network Time Service

[centos@ip-172-31-5-141 ~]$  systemctl list-units --type service|grep ntpd
ntpd.service                       loaded active running Network Time Service

