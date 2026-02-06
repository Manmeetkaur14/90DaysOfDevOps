Process management
A process is an instance of a program that is currently running in memory.


ps > Shows process Running in the current Terminal 

ps aux > Shows All process of all users including background processes with cpu and memory usage details

ps -ef > Shows All process in Full format including PPID

ps aux | grep Z > To check Dead process
ps aux | grep defunct > To check Dead process

Top 

Press 1 > Toggle between overall Cpu to Per-core Cpu usage
Press m > Sort Process by memeory usage
Press f/F > can add or remove customize fields 
Press T > sort by Time
Press K > Kill a process
Press r > Renice a process
Press U > Filter process by a specific process
Press H > Help Screen
Press q > Quit 
Shift + P → sort by CPU
Shift + M → sort by memory
-------------------------------------------------
ps -eo pid,ppid,cmd > To edit Process Output
----------------------------------------------
pidof > To check 
pgrep > get PID of process
pstree > process hierarchy
pstree -p 

“pstree shows parent–child process relationships, and pstree -p also displays process IDs.”

Kill PID   send signal to process 
Kill -l
SIGKILL kill -9 (Forcefull Kill, Terminate the process)
SIGTERM kill -15 (Kill process gracefully)
SIGSTOP kill -19 (Temporary state)
SIGCONT kill -18 (Resume process)

nice — start process with priority
nice -n 10 PID
renice -5 -p PID 


Jobs > List background jobs for the current shell
bg%1 > Resumes a stopped job in the background
fg%1 > Bringes a background job to the for