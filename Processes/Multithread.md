To view process threads, you can use:

pete@icebox:~$ ps m

   PID TTY      STAT   TIME COMMAND 

     2207 pts/2    -      0:01 bash

      - -        Ss     0:01 -

     5252 pts/2    -      0:00 ps m

      - -        R+     0:00 - 

    The processes are denoted with each PID and underneath the processes are their threads (denoted by a --) 


## Cpu monitoring 
    pete@icebox:~$ uptime

    Load averages are good way to see the CPU load on your system. 
    These numbers represent the average CPU load in 1, 5, and 15 minute intervals. 
    What do I mean by CPU load, the CPU load is the average number of processes that are waiting to be executed by the CPU.
