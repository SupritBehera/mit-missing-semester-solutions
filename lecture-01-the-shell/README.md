# Missing Semester

## Lecture 01 Solutions

### Exercise 1

```bash
> echo $SHELL
/usr/bin/zsh
```
I'm currently using the zsh shell

### Exercise 2

```bash
> mkdir /tmp/missing
```

### Exercise 3

The `touch` program can be used for updating the access and modification times of a file.
It is also used to create an empty file. Unlike `cat` which is often used to create a new file with content,
`touch` is used to create a new file without any content.

If `touch` is passed an argument that has a path of a file that exists, then it updates the file access and modification time to the current time

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
The next three letters `rw-` indicate that the current user has read and write permissions, but not executable permissions. 
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

### Exercise 8

The `chmod` command is used to set and modify the permissions of a file

### Exercise 
We can use `chmod` to give executable permissions to `./semester`

```bash
> chmod u+x semester
```
What this means is that for the user (that is everything before +, we can also have g for group, a for all, 
o for others, and also combine them for eg. chmod ug+x), give x that is executable permissions. (Doing chmod ug+rx would give read and executable permissions to the user and the group)

Now that we have given executable permissions to ./semester, we can now do

```bash
> ./semester
HTTP/2 200 
server: GitHub.com
content-type: text/html; charset=utf-8
last-modified: Thu, 31 Dec 2020 22:23:08 GMT
access-control-allow-origin: *
etag: "5fee4f4c-1e9f"
expires: Sat, 02 Jan 2021 20:16:16 GMT
cache-control: max-age=600
x-proxy-cache: MISS
x-github-request-id: C4DA:6AF8:16317E3:1B32C0D:5FF0D237
accept-ranges: bytes
date: Sun, 03 Jan 2021 07:06:55 GMT
via: 1.1 varnish
age: 302
x-served-by: cache-maa10244-MAA
x-cache: HIT
x-cache-hits: 1
x-timer: S1609657615.390908,VS0,VE0
vary: Accept-Encoding
x-fastly-request-id: 66152d47c0629c45fe3b23d1a656c84c7998b79b
content-length: 7839
```

The first line in ./semester is `#!/bin/sh`. `#` means that the line is ignored by bash, but `#!`, which is called a shebang, holds special meaning. A shebang at the top of a file tells the shell to run the script using the program at mentioned as an argument to `#!`. In this case, `#!/bin/sh` would run the program /bin/sh passing to it in the argument the path of the script, that is `/tmp/missing/semester`

### Exercise 10

