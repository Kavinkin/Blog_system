# Navigation(导航)

## File System Organization(文件系统组织)

The files on a linux systems are arranged in what is called a *hierarchical directory structure*.

This means that they are organized in a tree-like pattend of directories(called folders in other systems), which may contain files and *subdirectories*.

The first directory in the file system is called the *root directory*.The root directory contains files and subdirectories, which contain more files and subdirectories and so on and so on.

Most graphical environments include a file manager program used to view and manipulate the contents of the file system.

>One important diffence between Windows and Unix-like operating systems such as Linux is that Linux does not employ the concept of drive letters.
>Windows drive letters split the file system into a series of different trees (one for each device).
>Linux always has a single tree. Different storage devices may be different branches of the tree, but there is always just a single tree.

## pwd(print working directory)

Since the command line interface cannot provide pictures of the file system structure so we must repersenting in a different way.

At any given moment, we are located in a single directory. We can see its files and the pathway to its *parent directory* and the pathways to the subdirectories of the directory in which we are standing.

The directory we are standing in is the *working directory*.

```bash
[me@linuxbox me]$pwd
/home/me
```

When we first log on to our linux system,the working directory is set to our *home directory*. This is where we put our files. On most systems, the home directory will be called /home/user_name, but it can be anything according to the whims of the system administrator.

## cd(change directory)

To change the working directory.

To do this, we type `cd` followed by the *pathname* of the desire working directory.

A pathname is the route we take along the branches of the tree to the directory we want.

Most of them can be specified two different ways:

- absolute pathname(begins with the root directory and follows the tree branch by branch until the path to the desired directory or file is ccompleted, such as /user/bin)
- relative pathname(starts from the working directory and uses a couple of special notations to represent relative positions in the file system tree. These special notations are "."(dot) and ".."(dot dot).)

The dot notation refers to the working directory itself and the dot dot notation refers to the working directory's parent directory.

```bash
#relative pathname
cd ./bin
```

In most cases, we can omit the "./". It is implied.

>Shortcuts
>If we type `cd` followed by nothing, `cd` will change the directory to home directory.
>A related shortcut is to type `cd ~user_name`. In this case, `cd` will change the working directory to the home directory of the specified user.
>Typing `cd -` changes the working directory to the previous one.

## ls(list files and directory)

To list the files in the working directory.

## Important facts about file names

1. File names that begin with a period character are hidden. This only means that `ls` will not list them unless we say `ls -a`. When your account was created, several hidden files were placed in your home directory to configure things for account. Later on we will take a closer look at some of these files to see how you can customize our environment. In addition, some applications will place their configuration and settings files in your home directory as hidden files.

2. Fils names in Linux, like Unix, are case sensitive. The file names "Files 1" and "file 1" refer to different files.

3. Linux has no concept of a "file extension" like Windows. However, while Linux itself does not care about file extensions, many application programs do.

4. Linux only supports long file names which may contain period(句点), dash(短横线) and underscore(下划线). And **most importantly, do not embed spaces in file names**. Use underscore instead of use embed spaces.
