## root
    There is a file called the /etc/sudoers file, this file lists users who can run sudo. You can edit this file with the visudo command.
    root:x:0:0:root:/root:/bin/bash
    You can see many different symbols that are in this field, if you see an "x" that means the password is stored in the /etc/shadow file, 
    a "*" means the user doesn't have login access and if there is a blank field that means the user doesn't have a password.
    The user ID - as you can see root has the UID of 0
    The group ID
    GECOS field - This is used to generally leave comments about the user or account such as their real name or phone number, it is comma delimited.
    User's home directory
    User's shell - you'll probably see a lot of user's defaulting to bash for their shell

    The /etc/shadow file is used to store information about user authentication. It requires superuser read permissions. 
## /etc/shadow file
    - Username
    - Encrypted password
    - Date of last password changed - expressed as the number of days since Jan 1, 1970. If there is a 0 that means the user should change their password the next time they login
    - Minimum password age - Days that a user will have to wait before being able to change their password again
    - Maximum password age - Maximum number of days before a user has to change their password
    - Password warning period - Number of days before a password is going to expire
    - Password inactivity period - Number of days after a password has expired to allow login with their password
    - Account expiration date - date that user will not be able to login
    - Reserved field for future use
      In most distributions today, user authentication doesn't rely on just the /etc/shadow file, t
      here are other mechanisms in place such as PAM (Pluggable Authentication Modules) that replace authentication.


      Another file that is used in user management is the /etc/group file. This file allows for different groups with different permissions.

## $ cat /etc/group
    root:*:0:pete

    Very similar to the /etc/password field, the /etc/group fields are as follows:

    Group name
    Group password - there isn't a need to set a group password, using an elevated privilege like sudo is standard. A "*" will be put in place as the default value.
    Group ID (GID)
    List of users - you can manually specify users you want in a specific group

    to change user and group of file command:
    sudo chown patty:whales myfile

    Just like regular permissions there are two ways to modify SUID permissions.

Symbolic way:

    $ sudo chmod u+s myfile
    Numerical way:

    sudo chmod 4755 myfile
     SUID is denoted by a 4
     SUID denoted as a capital S this means that it still does the same thing, but it does not have execute permissions.

     sudo chmod g+s myfile
     The numerical representation for SGID is 2.
    $ sudo chmod 2555 myfile


     There are three UIDS associated with every process:

     When you launch a process, it runs with the same permissions as the user or group that ran it, this is known as an effective user ID. This UID is used to grant access rights to a process. So naturally if Bob ran the touch command, the process would run as him and any files he created would be under his ownership.

    There is another UID, called the real user ID this is the ID of the user that launched the process. These are used to track down who the user who launched the process is.

    One last UID is the saved user ID, this allows a process to switch between the effective UID and real UID, vice versa. This is useful because we don't want our process to run with elevated privileges all the time, it's just good practice to use special privileges at specific times.

    Now let's piece these all together by looking at the passwd command once more.

    When running the passwd command, your effective UID is your user ID, let's say its 500 for now. Oh but wait, remember the passwd command has the SUID permission enabled. So when you run it, your effective UID is now 0 (0 is the UID of root). Now this program can access files as root.

    Let's say you get a little taste of power and you want to modify Sally's password, Sally has a UID of 600. Well you'll be out of luck, fortunately the process also has your real UID in this case 500. It knows that your UID is 500 and therefore you can't modify the password of UID of 600. (This of course is always bypassed if you are a superuser on a machine and can control and change everything).

    Since you ran passwd, it will start the process off using your real UID, and it will save the UID of the owner of the file (effective UID), so you can switch between the two. No need to modify all files with root access if it's not required.

    Most of the time the real UID and the effective UID are the same, but in such cases as the passwd command they will change.
