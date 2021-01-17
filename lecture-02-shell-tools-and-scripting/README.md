# Missing Semester

## Lecture 02 Solutions

### Exercise 1

From `man ls`, the appropriate flags for :

- Includes all files, including hidden files : `-a`
- Sizes are listed in human readable format : `-h`
- Files are ordered by recency : `-t`
- Output is colorized : `--color`

To list the files in the way the output specifies, we use the `-l` flag

Henceforth the appropriate `ls` command to achieve so would be :
`ls -ahlt --color`

```bash
$ ls -ahtl --color ~/Books/Programming/C-C++/ 
total 203M
drwxr-xr-x 6 suprit suprit 4.0K Jan 17 12:00  ..
-rw-r--r-- 1 suprit suprit 2.2M Jan 17 11:58 'Accelerated C++.pdf'
drwxr-xr-x 2 suprit suprit 4.0K Jan 17 11:58  .
-rw-r--r-- 1 suprit suprit 4.5M Jan 17 11:55 'Effective Modern C++ 42 Specific Ways to Improve Your Use of C++11 and C++14 by Scott Meyers.pdf'
-rw-r--r-- 1 suprit suprit  19M Jan 17 11:51 'The C++ Programming Language, 4th Edition by Bjarne Stroustrup.pdf'
-rw-r--r-- 1 suprit suprit  51M Jan 17 11:51 'C++ Primer (5th edition).pdf'
-rw-r--r-- 1 suprit suprit  20M Jan 17 11:47 'Programming principles and practice using C++ by Stroustrup, Bjarne.pdf'
-rw-r--r-- 1 suprit suprit 102M Jan  9 12:26 'K. N. King - C Programming_ A Modern Approach-W. W. Norton & Company (2008).pdf'
-rw-r--r-- 1 suprit suprit 3.4M Dec  4 10:26 'Let Us C.pdf'
-rw-r--r-- 1 suprit suprit 2.8M Aug 24 00:39 'Brian W. Kernighan, Dennis M. Ritchie - The ANSI C Programming Language-Prentice Hall (1988).pdf'
```
- 
