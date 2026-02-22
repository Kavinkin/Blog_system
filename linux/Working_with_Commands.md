# Working with Commands

# Commands

Commands can be one of 4 different kinds:

1. **An executable program** like all those files we saw in /usr/bin. Within this category, programs can be compiled binaries such as programs written in C and C++, or programs written in scripting languages such as the shell, Perl, Python, Ruby, etc。
2. **A command built into the shell itself.** Bash provide a number of commands internally called shell builtins. The **cd** command, for example, is a shell builtin.
3. **A shell function**. These are miniature shell scripts incorporated into the environment.
4. **An alias**. Commands that we can define ourselvs, built from other commands.

## Identifying Commands

It is often useful to know exactly which of four kinds of commands is being used and Linux provides a couple of ways to find out.

### type

The type command is a shel builtin that displays the kind of command the shell will execute, given a particular command name.

```bash
type command
```

Where "command" is the name of the command we want to examine
```bash
[me@linuxbox me]$ type type
type is a shell builtin
[me@linuxbox me]$ type ls
ls is aliased to `ls --color=auto'
[me@linuxbox me]$ type cp
cp is /bin/cp
```



### which
