# 24 Writing Your First Scirpt

## What Are Shell Scripts?

## How to Write a Shell Script

1. Write a script.
1. Make the script executable.
1. Put the script somewhere the shell can find it.

### Script FIle Format

````bash
#!/bin/bash

# This is our first script.

echo 'Hello World!'
``

One thing about comments in shell scripts is that they may appear at the ends of lines provided they are preceded by at least one white space character, like so:
`echo 'Hello World!' # This is a comment too`

Like many things, this works on the command line too:
`[me@linuxbox ~]$ echo 'Hello World!' # THis is a comment too`

Save the script as **hello_world**.

### Executable Permissions

```bash
chmod 755 hello_world
````

### Script File Location

Locate the script file in a directory contained in PATH, commonly it is located in a _bin_ direcotry in the user's home directory.

### Good Locations for Scripts

**~/bin** is a good place to put scripts intended for personal use.

## More Formatting Tricks

One of the key goals of serious script writing is ease of maintenance.

### Long Options Names

Short form: `ls -ad`  
Long form: `ls --all --directory`

> Short options are prefered when entering options on the command line.  
> Long options can improve readability when writing scrips.

### Indentation and Line Continuation

`find . \( -type f -not -perm 0644 -exec echo chmod 0644 '{}' ';' \) -or \( -type d -not -perm 0700 -exec echo chmod 0700 '{}' ';' \)`

In a script, this command might be easier to understand if written this way:

```bash
find . \
    \( \
        -type f \
        -not -perm 0644 \
        -exec echo chmod 0644 '{}' ';' \
        \) \
    -or \
    \( \
        -type d \
        -not -perm 0700 \
        -exec echo chmod 0700 '{}' ';' \
    \)
```
