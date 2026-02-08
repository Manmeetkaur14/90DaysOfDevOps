Environment basics:

Command : uname -a  

observations : shows kernel version information 


Command : cat /etc/os-release : 
observations : To see kernel Operating system information in details 

---------------
Filesystem sanity 

mkdir /tmp/runbook-demo
cp /etc/hosts /tmp/runbook-demo/hosts-copy && ls -l /tmp/runbook-demo

output: Created directory , 
hosts  hosts-copy
--------------------------
top 

output : 

top - 17:53:25 up  1:45,  2 users,  load average: 0.00, 0.02, 0.00
Tasks: 102 total,   1 running, 101 sleeping,   0 stopped,   0 zombie
%Cpu(s):  0.0 us,  0.0 sy,  0.0 ni, 94.6 id,  0.0 wa,  0.0 hi,  0.0 si,  5.4 st
MiB Mem :    961.4 total,    227.0 free,    165.6 used,    568.8 buff/cache
MiB Swap:      0.0 total,      0.0 free,      0.0 used.    630.8 avail Mem

    PID USER      PR  NI    VIRT    RES    SHR S  %CPU  %MEM     TIME+ COMMAND
      1 root      20   0  108468  18908  10788 S   0.0   1.9   0:01.28 systemd
      2 root      20   0       0      0      0 S   0.0   0.0   0:00.00 kthreadd
      3 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 rcu_gp
      4 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 rcu_par_gp
      5 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 slub_flushwq

------------------------------------------

ps -o pid,pcpu,pmem,comm -p 2134
    PID %CPU %MEM COMMAND
   2134  0.0  0.8 sshd

-----------------------------------------
 free -h
               total        used        free      shared  buff/cache   available
Mem:           961Mi       165Mi       226Mi       0.0Ki       568Mi       630Mi
Swap:             0B          0B          0B

---------------------------------------------------------
iostat :
“iostat is used to monitor CPU and disk I/O performance.”

vmstat
“vmstat is used to monitor memory, CPU, and system performance.”
-----------------------------------------------

Network 

netstat -tunlp | grep :22
ss -tunlp -tunlp | grep :22

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

