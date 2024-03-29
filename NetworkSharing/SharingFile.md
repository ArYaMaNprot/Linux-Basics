One simple file sharing tool is the scp command. 
The scp command stands for secure copy, it works exactly the way the cp command does, 
but allows you to copy from one host over to another host on the same network. 
It works via ssh so all your actions are using the same authentication and security as ssh.

## To copy a file over from local host to a remote host

    $ scp myfile.txt username@remotehost.com:/remote/directory
## To copy a file from a remote host to your local host
    $ scp username@remotehost.com:/remote/directory/myfile.txt /local/directory
    
## To copy over a directory from your local host to a remote host
    $ scp -r mydir username@remotehost.com:/remote/directory
