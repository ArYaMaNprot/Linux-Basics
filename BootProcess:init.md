This is the first process that gets started and it starts all the other essential services on our system. But how?

    There are actually three major implementations of init in Linux:

    System V init (sysv)

    This is the traditional init system. It sequentially starts and stops processes, based on startup scripts. The state of the machine is denoted by runlevels, each runlevel starts or stops a machine in a different way.

## Upstart

    This is the init you'll find on older Ubuntu installations.
    Upstart uses the idea of jobs and events and works by starting jobs that performs certain actions in response to events.

## Systemd

    This is the new standard for init, it is goal oriented. 
    Basically you have a goal that you want to achieve and systemd tries to satisfy the goal's dependencies to complete the goal.
