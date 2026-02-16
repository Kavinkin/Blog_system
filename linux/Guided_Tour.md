# Guided Tour

|Directory|Description|
|---------|-----------|
|/|The root directory where the file system begins. The root directory will probably contain only subdirectories|
|/boot|This is where the Linux kernel and boot loader files are kept.The kernel is a file called **vmlinuz**.|
|/etc|Contains the configuration files for the system. All of the files in **/etc** should be text files. <br>**/etc/passwd**<br>The passwd file contains the essential information for each user.This is where user accounts are defined.<br>**/etc/fstab**<br>The fstab file contains a table of decices that get mounted when the system boots.Defines the system's disk drives.<br>**/etc/hosts**<br>This file lists the network host names and IP addresses that are intrinsically known to the system.<br>**/etc/init.d**<br>This directory contains the scripts that start various system services at boot time.|
|/usr|The */usr* directory contains a variety of things that support usr applications. |
|/usr/local|*/usr/local* and its subdirectories are used for the installation of software and other files for use on the local machine. Means that software that is not part of the official distribution(which usually goes in */usr/bin*) goes here.<br><br>Most of time, the directory of programs to install on system usually choice */usr/local/bin*|
|/var|The */var* directory contains files that changes as the system