## tar and gzip
    Before we get into package installation and the different managers, we need to discuss archiving and compressing files, 
    because you will most likely encounter these when you hunt for software on the internet.

    You probably already know what a file archive is, you've most likely encountered file types such as .rar and .zip. 
    These are an archive of files, they contain many files inside of them, but they come in this very neat single file known as an archive.

## Compressing files with gzip

    gzip is program used to compress files in Linux, they end in a .gz extension.

    To compress a file down:

    $ gzip mycoolfile
    To decompress the file:

    $ gunzip mycoolfile.gz
## Creating archives with tar
    Unfortunately, gzip can't add multiple files into one archive for us. 
    Luckily we have the tar program which does. When you create an archive using tar, it will have a .tar extension.

    $ tar cvf mytarfile.tar mycoolfile1 mycoolfile2
    c - create
    v - tell the program to be verbose and let us see what it's doing
    f - the filename of the tar file has to come after this option, if you are creating a tar file you'll have to come up with a name
## Unpacking archives with tar

    To extract the contents of a tar file, use:

    $ tar xvf mytarfile.tar
    x - extract
    v - tell the program to be verbose and let us see what it's doing
    f - the file you want to extract
## Compressing/uncompressing archives with tar and gzip

     Many times you'll see a tar file that has been compressed such as: mycompressedarchive.tar.gz, 
     all you need to do is work outside in, so first remove the compression with gunzip and then you can unpack the tar file. 
     Or you can alternatively use the z option with tar, which just tells it to use the gzip or gunzip utility.

## Create a compressed tar file:

    $ tar czf myfile.tar.gz
    Uncompress and unpack:

    $ tar xzf file.tar
    If you need help remember this: eXtract all Zee Files!

    tar is one of those commands that is so important and yet you never really remember it, relevant xkcd: https://xkcd.com/1168/

## Other Utilities

    Throughout your journey of Linux, you'll encounter other archive and compression types such as: bzip2, compress, zip, unzip, etc. 
    They are a little less common, but just keep in mind that different utilities will call for different commands.
## Install a package
    Debian: $ dpkg -i some_deb_package.deb
    RPM: $ rpm -i some_rpm_package.rpm
    The i stands for install. You can also use the longer format of --install.

## Remove a package
    Debian: $ dpkg -r some_deb_package.deb
    RPM: $ rpm -e some_rpm_package.rpm
    Debian: r for remove
    RPM: e for erase

## List installed packages
    Debian: $ dpkg -l
    RPM: $ rpm -qa
    
## Debian: l for list
    RPM: q for query and a for all

# 6. yum and apt
    Ah, the Batmans of package management, these systems come with all the fixins to make package installation,
    removal and changes easier, including installing package dependencies. Two of the most popular management systems is yum and apt. 
    Yum is exclusive to the Red Hat family and apt is exclusively to the Debian family.

    Install a package from a repository


    Debian: $ apt install package_name

    RPM: $ yum install package_name

    Remove a package


    Debian: $ apt remove package_name

    RPM: $ yum erase package_name

    Updating packages for a repository

    It's always best practice to update your package repositories so they are up to date before you install and update a package.


    Debian: apt update; apt upgrade

    RPM: yum update

    Get information about an installed package


    Debian: apt show package_name

    RPM: yum info package_name
