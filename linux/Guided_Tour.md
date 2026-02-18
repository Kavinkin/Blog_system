# Guided Tour

|Directory|Description|
|---------|-----------|
|/|The root directory where the file system begins. The root directory will probably contain only subdirectories|
|/boot|This is where the Linux kernel and boot loader files are kept.The kernel is a file called **vmlinuz**.|
|/etc|Contains the configuration files for the system. All of the files in **/etc** should be text files. <br>**/etc/passwd**<br>The passwd file contains the essential information for each user.This is where user accounts are defined.<br>**/etc/fstab**<br>The fstab file contains a table of decices that get mounted when the system boots.Defines the system's disk drives.<br>**/etc/hosts**<br>This file lists the network host names and IP addresses that are intrinsically known to the system.<br>**/etc/init.d**<br>This directory contains the scripts that start various system services at boot time.|
|/usr|The */usr* directory contains a variety of things that support usr applications. |
|/usr/local|*/usr/local* and its subdirectories are used for the installation of software and other files for use on the local machine. Means that software that is not part of the official distribution(which usually goes in */usr/bin*) goes here.<br><br>Most of time, the directory of programs to install on system usually choice */usr/local/bin*|
|/var|The */var* directory contains files that changes as the system is running.<br><br>*/var/log*<br><br>Directory that contains log files.Updated as the system runs.<br><br>*/var/spool*<br><br>Used to hold files that queued for some process, such as mail messages and print jobs.|
|/lib|The shared libraries(similar to DLLs in that other operating system) are kept here|
|/home|Keep personal work. In general, this is the only place users are allowed to write files. To keeps system clean.|
|/root|The superuser's home directory.|
|/tmp|A directory in which programs can write their temporary.|
|/dev|The */dev* directory is a special directory, since it does not really contain files in the usual sense. Rather, it contains devices that are available to the system. In linux (like Unix), devices are treated like files. So you can read and write devices as though they were files. For example */dev/fd0* is the first floppy disk drive, */dev/sda* is the first hard drive. All the devices that the kernel understands are represented here.|
|/proc|The */proc* directory is also special. This directory does not contain files and even not really exist at all. It is entirely virtual. The */proc* directory contains little peep holes into the kernel itself. There are a group of numbered entries in this directory that correspond to all the processes running on the system. In addition, there are a number of named entries that permit access to the current configuration of the system. Many of these entries can be viewed. Such as */proc/cpuinfo*. This entry will show you what the kernel thinks of the system's CPU|
|/media|A normal directory which is used in a special way. The */media* directory is used for **mount point**. The different physical storage devices (like hard disk drives) are attached to the file system tree in various places. This process of attaching a device to the treee is called **mounting**. For a device to be available, it must first be mounted.<br><br>When system boots, it reads a list of mounting instructions in the **/etc/fstab** file, which describe which device is mounted at which mount point in the directory tree. This takes care of the hard drives, but we may also have devices that are considered temporary, such as optical disks and USB storage devices. Since these are removable, they do not stay mounted all the time. The **/media** directory is used by the automatic device mounting mechanisms found in modern desktop oriented Linux distributions. To see what devices and mount points are used, type **mount**.|

## Symbolic links

In **/lib** directory, When listd with `ls -l`, you might have seen something like this.

```bash
lrwxrwxrwx     25 Jul  3 16:42 System.map -> /boot/System.map-4.0.36-3
-rw-r--r-- 105911 Oct 13  2018 System.map-4.0.36-0.7
-rw-r--r-- 105935 Dec 29  2018 System.map-4.0.36-3
-rw-r--r-- 181986 Dec 11  2019 initrd-4.0.36-0.7.img
-rw-r--r-- 182001 Dec 11  2019 initrd-4.0.36.img
lrwxrwxrwx     26 Jul  3 16:42 module-info -> /boot/module-info-4.0.36-3
-rw-r--r--  11773 Oct 13  2018 module-info-4.0.36-0.7
-rw-r--r--  11773 Dec 29  2018 module-info-4.0.36-3
lrwxrwxrwx     16 Dec 11  2019 vmlinuz -> vmlinuz-4.0.36-3
-rw-r--r-- 454325 Oct 13  2018 vmlinuz-4.0.36-0.7
-rw-r--r-- 454434 Dec 29  2018 vmlinuz-4.0.36-3
```

Notice the file, System.map, module-info and vmlinuz. Such as these are called *symbolic links*. A special type of file that points to another file.

Symbolic link is essentially the Unix/Linux equivalent of **Windows shortcut** or **MacOS alias**.

With symbolic links, it is possible for q single file to have mutiple names.

Whenever the system is given a file name that is a symbolic link, it transparenly maps it to the file it is pointing to.

For example, when system has had multiple versions of Linux kernel installed. We can see this from the files vmlinuz-4.0.36-0.7 and vmlinuz-4.0.36-3. These file names suggest that both version are installed. Because the file names contain the version it is easy to see the differences in the directory listing. But this would be confusing to programs that rely on a fixed name for kernel file. These programs might expect the kernel to simply be called "vmlinuz". By creating a symbolic link called vmlinuz that points to vmlinuz-4.0.36-3.