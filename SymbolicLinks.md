# Symlinks
    In the Windows operating system, there are things known as shortcuts, shortcuts are just aliases to other files. 
    If you do something to the original file, you could potentially break the shortcut. 
    In Linux, the equivalent of shortcuts are symbolic links (or soft links or symlinks). 
    Symlinks allow us to link to another file by its filename. 
    Another type of links found in Linux are hardlinks, these are actually another file with a link to an inode. 
    Let's see what I mean in practice starting with symlinks.

    symlinks are just files that point to filenames. When you modify a symlink, 
    the file also gets modified. 
    Inode numbers are unique to filesystems, you can't have two of the same inode number in a single filesystem, meaning you can't reference a file in a different filesystem by its inode number. 
    However, if you use symlinks they do not use inode numbers, they use filenames, so they can be referenced across different filesystems.

    A hardlink just creates another file with a link to the same inode. 
    So if I modified the contents of myfile2 or myhardlink, the change would be seen on both, but if I deleted myfile2, 
    the file would still be accessible through myhardlink. Here is where our link count in the ls command comes into play. 
    The link count is the number of hardlinks that an inode has, when you remove a file, it will decrease that link count. 
    The inode only gets deleted when all hardlinks to the inode have been deleted. 
    When you create a file, it's link count is 1 because it is the only file that is pointing to that inode. 
    Unlike symlinks, hardlinks do not span filesystems because inodes are unique to the filesystem.
    Creating a symlink


    $ ln -s myfile mylink
    To create a symbolic link, you use the ln command with -s for symbolic and you specific a target file and then a link name.

    Creating a hardlink


    $ ln somefile somelink
    Similar to a symlink creation, except this time you leave out the -s.

