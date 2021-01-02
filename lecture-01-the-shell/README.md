# Missing Semester

-------------------------------------------------------------------------------

## Lecture 01 Solutions

### Exercise 1

```bash
> echo $SHELL
/usr/bin/zsh
```
I'm currently using the zsh shell

### Exercise 2

```bash
> cd /temp
> mkdir /tmp/missing
```

### Exercise 3

The `touch` program can be used for updating the access and modification times of a file.
It is also used to create an empty file. Unlike `cat` which is often used to create a new file with content,
`touch` is used to create a new file without any content. 

### Exercise 4

```bash
> touch /tmp/missing/semester
```
### Exercise 5

```bash
> cd /tmp/missing
> echo '#!/bin/sh' > semester
> echo 'curl --head --silent https://missing.csail.mit.edu' >> semester
```

### Exercise 6

```bash
> ls -l /tmp/missing 
.rw-r--r-- 61 suprit  3 Jan  1:35 semester
```
The `.` indicates that semester is a file
The next three letters ``rw-` indicate that the current user has read and write permissions, but not executable permissions. 
These are the default permissions of any empty file created using `touch`

Hence on running `./semester`, the shell tries to execute semester, but since we do not have execution permissions, we cannot do so

### Exercise 7

When we do `sh ./semester`, the shell executes the `sh` program.

```bash
> ls -l $(which sh)
lrwxrwxrwx 4 root 12 Dec  2020 /usr/bin/sh -> bash
```
We can see that the sh program in /usr/bin has rwx permissions for the user (oh and here the l means symbolic link)
and hence can be run and executed directly from the shell.

We pass the ./semester file as an argument to the sh program, which itself has executable permissions, and hence `sh semester` works

