# Manipulating File

- cp(copy files and directories)
- mv(move or rename files directories)
- rm(remove files and directories)
- mkdir(create directories)

```bash
[me@linuxbox me]$ cp -u *.html destination
```

# Wildcard(通配符)

Also called **globbing pattens**. Because early Unix has a file `/etc/glob` to save modle of wildcards, and bash orginally has this function, but the name stay.

These are the shell feature that makes these commands so powerful. Since the sell uses filenames so much, it provided special characters to help us rapidly specify groups of filenames called wildcards.

These allow us to select filenames based on patterns of characters.

| Wildcard | Meaning |
|----------|---------|
| `*` | Matches any characters |
| `?` | Matches any single character |
| `[characters]` | Matches any character that is a member of the set *characters*. The set of characters may also be expressed as a POSIX *character class* such as one of the following:<br><br>\| POSIX Class \| Description \|<br>\|-------------\|-------------\|<br>\| `[:alnum:]` \| Alphanumeric characters \|<br>\| `[:alpha:]` \| Alphabetic characters \|<br>\| `[:digit:]` \| Numerals \|<br>\| `[:upper:]` \| Uppercase alphabetic characters \|<br>\| `[:lower:]` \| Lowercase alphabetic characters \|<br><br>*POSIX Character Classes* |
| `[!characters]` | Matches any character that is not a member of the set *characters* |

## Using wildcards

Using wildcards, it is possible to construct very sophisticated criteria for filenames.

|Pattern|Matches|
|-----|-----|
|*|All filenames|
|g*|All filenames that begin with character "g"|
|b*.txt|All filenames that begin with charater "b" and end with the characters ".txt"|
|Data???|All filenames that begins with the characters "Data" follow by exactly 3 more characters|
|[abc]*|Any filename that begin with "a" or "b" or "c" follow by any other characters|
|`[[:upper:]]*`|Any filename that begins with an uppercase letter. This is an example of characters class|
|`BACKUP.[[:digit:]]`|Another example of character classes. This pattern matches any filename that begins with the characters "BACKUP." followed by exactly two numerals|
|`*[![:lower:]]`|Any filename that does not end with a lowercase letter|

We can use wildcards with any command that accepts filename arguments.

# cp

The `cp` program copies files and directories. In its simplest form, it copies a single file:

```bash
#single
#copies the contents of file1 into file2. If file2 does not exist, it is created
cp file1 file2

#since the `-i` (interactive) option is specified, if file 2 exists, the user is prompted before it is overwritten with the contents of file1
cp -i file1 file2

#copy the contents of file1(into a file named file1) inside of directory dir1
cp file1 dir1

#copy the contents of the directory dir1. If directory dir2 does not exist, it is created. Otherwise, it creates a directory named dir1 within directory dir2
cp -R dir1 dir2

#copy multiple files (and/or directories) to a different directory
cp file... directory

#eg:
#copy two files to `backup/` directory
cp test1.txt test2.txt backup/

#copy `test1.txt` and `docs/` directory to `backup/` directory
cp -r test1.txt docs/ backup/
```

`...` signfies that an item can be repeated one or more times.

# mv

The `mv` command moves or renames files and directories depending on how it is used.