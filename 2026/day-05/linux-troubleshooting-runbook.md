Environment basics:

Command : uname -a  

observations : shows kernel version information 


Command : cat /etc/os-release : 
observations : To see kernel Operating system information in details 

---------------
Filesystem sanity 

mkdir /tmp/runbook-demo
cp /etc/hosts /tmp/runbook-demo/hosts-copy && ls -l /tmp/runbook-demo

observations : Created directory , copied Files from one path to other then listed it now shows two files
hosts  hosts-copy
--------------------------
command : top 

observations : is used to check real time Process running in the system

------------------------------------------

command : ps -o pid,pcpu,pmem,comm -p 2134

observations : ps is used to see process to custom output we edited fields PID %CPU %MEM COMMAND
   2134  0.0  0.8 sshd

-----------------------------------------
commands : free -h

observations : Its shows Memory details and swap free , used , shared , available 

---------------------------------------------------------
iostat :
“iostat is used to monitor CPU and disk I/O performance.”

vmstat
“vmstat is used to monitor memory, CPU, and system performance.”
-----------------------------------------------

Network 

commands : netstat -tunlp | grep :22
commands : ss -tunlp -tunlp | grep :22

obesrvations : is used to check listening service ports

command : ping
ping to check connectivity between two servers


curl -I http://example.com

----------------------------------------
 tail -n 50 /var/log/hawkey.log
2026-02-08T16:07:57+0000 INFO === Started libdnf-0.69.0 ===
2026-02-08T16:44:23+0000 INFO === Started libdnf-0.69.0 ===
2026-02-08T16:44:35+0000 INFO === Started libdnf-0.69.0 ===

---------------------------------

journalctl -u sshd -n 50
Feb 08 16:07:54 ip-172-31-3-68.ap-south-1.compute.internal systemd[1]: Starting sshd.service - OpenSSH server daemon...
Feb 08 16:07:54 ip-172-31-3-68.ap-south-1.compute.internal sshd[2134]: Server listening on 0.0.0.0 port 22.
Feb 08 16:07:54 ip-172-31-3-68.ap-south-1.compute.internal sshd[2134]: Server listening on :: port 22.
Feb 08 16:07:54 ip-172-31-3-68.ap-south-1.compute.internal systemd[1]: Started sshd.service - OpenSSH server daemon.

--------------------------

