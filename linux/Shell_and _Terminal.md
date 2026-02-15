# Shell

## What is shell

Shell is a program that takes commands from the keyboard and gives them to the operating system to perform.

So we have graphical user interfaces(GUI) (图形用户界面) and command line interfaces(CLI)

On most Linux systems a program called *bash* (Bourne Again Shell, an enhanced version of original Unix shell program) acts as the shell program.

There are other shell program available for linux systems include *ksh*,*tcsh* and *zsh*.

## Terminal

A program called a *terminal emulator* that opens a window and lets you interact with the shell.

These might include *gnome-terminal*, *konsole*, *xterm*, *rxvt*, *kvt*, *nxterm* and *eterm*.

They give us access to a shell session.

When we bring up a terminal window, the first thing is a *shell prompt* that contains user name and name of the machine followed by a dollar sign($).

### Operating as root

If the last character of shell prompt is # rather than $, means you are operating as the superuser and you have administrative privileges.

It's dangerous, since you are able to delete or overwrite any file on the system.

Unless you absolutely need administrative privileges, do not operate as the superuesr.

### focus

When install Linux system and its window manager (most likely Gnome or KDE), is was configured to behave in some ways like that legacy system.

In particular, it probably has its *focus policy* set to "click to focus"(become active). This is contrary to tradidional X Window behavior. To without having the active window obscuring the other.

The opposite mode is focus follows mouse / fovor focus. Means that move mouse over a window.