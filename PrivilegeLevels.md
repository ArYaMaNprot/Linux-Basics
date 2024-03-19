In kernel mode, the kernel has complete access to the hardware, it controls everything. 
In user space mode, there is a very small amount of safe memory and CPU that you are allowed to access. 
Basically, when we want to do anything that involves hardware, reading data from our disks,
writing data to our disks, controlling our network, etc, it is all done in kernel mode.

These different modes are called privilege levels (aptly named for the levels of privilege you get) and are often described as protection rings. 
To make this picture easier to paint, let's say you find out that Britney Spears is in town at your local klerb,
she's protected by her groupies, then her personal bodyguards, then the bouncer outside the klerb. 
You want to get her autograph (because why not?), but you can't get to her because she is heavily protected. 
The rings work the same way, the innermost ring corresponds to the highest privilege level.
There are two main levels or modes in an x86 computer architecture.
Ring #3 is the privilege that user mode applications run in, Ring #0 is the privilege that the kernel runs in. 
Ring #0 can execute any system instruction and is given full trust. 

 system calls allow us to perform a privileged instruction in kernel mode and then switch back to user mode.
