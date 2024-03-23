## 1st line: This is the same information you would see if you ran the uptime command (more to come)

    The fields are from left to right:

      Current time
      How long the system has been running
      How many users are currently logged on
      System load average (more to come)
      2nd line: Tasks that are running, sleeping, stopped and zombied

## 3rd line: Cpu information

    us: user CPU time - Percentage of CPU time spent running users’ processes that aren’t niced.
    sy: system CPU time - Percentage of CPU time spent running the kernel and kernel processes
    ni: nice CPU time - Percentage of CPU time spent running niced processes
    id: CPU idle time - Percentage of CPU time that is spent idle
    wa: I/O wait - Percentage of CPU time that is spent waiting for I/O. If this value is low, the problem probably isn’t disk or network I/O
    hi: hardware interrupts - Percentage of CPU time spent serving hardware interrupts
    si: software interrupts - Percentage of CPU time spent serving software interrupts
    st: steal time - If you are running virtual machines, this is the percentage of CPU time that was stolen from you for other tasks
    4th and 5th line: Memory Usage and Swap Usage

## Processes List that are Currently in Use

      PID: Id of the process
      USER: user that is the owner of the process
      PR: Priority of process
      NI: The nice value
      VIRT: Virtual memory used by the process
      RES: Physical memory used from the process
      SHR: Shared memory of the process
      S: Indicates the status of the process: S=sleep, R=running, Z=zombie,D=uninterruptible,T=stopped
      %CPU - this is the percent of CPU used by this process
    %MEM - percentage of RAM used by this process
    TIME+ - total time of activity of this process
    COMMAND - name of the process
    You can also specify a process ID if you just want to track certain processes:

    $ top -p 1
