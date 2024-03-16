  The fsck (filesystem check) command is used to check the consistency of a filesystem and can even try to repair it for us. 
  Usually when you boot up a disk, fsck will run before your disk is mounted to make sure everything is ok. 
  Sometimes though, your disk is so bad that you'll need to manually do this. 
  However, be sure to do this while you are in a rescue disk or somewhere where you can access your filesystem without it being mounted.

    $ sudo fsck /dev/sda
