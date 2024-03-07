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
