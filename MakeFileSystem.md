  Now that you've actually partitioned a disk, let's create a filesystem!

    $ sudo mkfs -t ext4 /dev/sdb2
    Simple as that! The mkfs (make filesystem) tool allows us to specify the type of filesystem we want and where we want it. 
    You'll only want to create a filesystem on a newly partitioned disk or if you are repartitioning an old one. 
    You'll most likely leave your filesystem in a corrupted state if you try to create one on top of an existing one.
