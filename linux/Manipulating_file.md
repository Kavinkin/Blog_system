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

|wildcard|Meaning|
|-----|-----|
|*|Matches any characters|
|?|Matches any single character|
|[characters]|Matches any character that is member of the set characters. The set of characters may also be expressed as a POSIX character class such as one of the following
<br>
- [:alnum:]