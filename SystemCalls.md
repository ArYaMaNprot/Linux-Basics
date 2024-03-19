System calls (syscall) provide user space processes a way to request the kernel to do something for us. 
The kernel makes certain services available through the system call API. 
These services allow us to read or write to a file, modify memory usage,modify our network, etc. 
The amount of services are fixed, so you can't be adding system calls nilly willy, 
your system already has a table of what system calls exist and each system call has a unique ID.
