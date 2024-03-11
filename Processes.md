# Processes
    Processes are the programs that are running on your machine. 
    They are managed by the kernel and each process has an ID associated with it called the process ID (PID). 
    This PID is assigned in the order that processes are created.

    PID: Process ID
    TTY: Controlling terminal associated with the process (we'll go in detail about this later)
    STAT: Process status code
    TIME: Total CPU usage time
    CMD: Name of executable/command

    $ ps aux
    
    The a displays all processes running, including the ones being ran by other users. The u shows more details about the processes. 
    And finally the x lists all processes that don't have a TTY associated with it, these programs will show a ? in the TTY field, 
    they are most common in daemon processes that launch as part of the system startup.

    You'll notice you're seeing a lot more fields now, no need to memorize them all, in a later course on advanced processes, 
    we'll go over some of these again:

    USER: The effective user (the one whose access we are using)
    PID: Process ID
    %CPU: CPU time used divided by the time the process has been running
    %MEM: Ratio of the process's resident set size to the physical memory on the machine
    VSZ: Virtual memory usage of the entire process
    RSS: Resident set size, the non-swapped physical memory that a task has used
    TTY: Controlling terminal associated with the process
    STAT: Process status code
    START: Start time of the process
    TIME: Total CPU usage time
    COMMAND: Name of executable/command


## process creation

    When a new process is created, an existing process basically clones itself using something called the fork system call (system calls will be discussed very far into the future). The fork system call creates a mostly identical child process, this child process takes on a new process ID (PID) and the original process becomes its parent process and has something called a parent process ID PPID. Afterwards, the child process can either continue to use the same program its parent was using before or more often use the execve system call to launch up a new program. This system call destroys the memory management that the kernel put into place for that process and sets up new ones for the new program.
