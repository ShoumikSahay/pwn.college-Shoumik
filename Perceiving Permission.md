# Module 11. Perceiving Permissions
## 11.1 Changing ownership
## What I did
```
hacker@permissions~changing-file-ownership:~$ chown hacker /flag
hacker@permissions~changing-file-ownership:~$ cat /flag
pwn.college{Q8Yicacy6ZaKMBGjazzagPucLGe.QXxEjN0wSN3kjNzEzW}

```
## Flag
pwn.college{Q8Yicacy6ZaKMBGjazzagPucLGe.QXxEjN0wSN3kjNzEzW}
                    
## What I learned
I learned that file ownership controls who can read a file, and that chown changes a file’s owner so I (as the new owner) could read /flag. By changing ownership to my user and then cat-ing the file, 
I was able to access the flag — and I also learned that chown normally requires elevated privileges, so I should use it carefully.

## 11.2 Griups and Files
## What I did
```
hacker@permissions~groups-and-files:~$ chgrp hacker /flag
hacker@permissions~groups-and-files:~$ cat /flag
pwn.college{Ep1Z3FrlRkk9wjWAeyPTqcueIqZ.QXxcjM1wSN3kjNzEzW}
```
## Flag
pwn.college{Ep1Z3FrlRkk9wjWAeyPTqcueIqZ.QXxcjM1wSN3kjNzEzW}
                    
## What I learned
I learned that file group ownership controls access just like the file owner does: chgrp hacker /flag changes the file’s group to hacker, and if the group has 
read permission I can then cat /flag to read it. I also learned that changing group/owner typically requires elevated privileges and should be used carefully, 
because altering ownership or group membership can expose sensitive files.


## 11.3 Fun with Group Names
## What I did
```
hacker@permissions~fun-with-groups-names:~$ id
uid=1000(hacker) gid=1000(grp14089) groups=1000(grp14089)
hacker@permissions~fun-with-groups-names:~$ chgrp grp14089 /flag
hacker@permissions~fun-with-groups-names:~$ cat /flag
pwn.college{oHwFR2zDu--ybI7eeAZdB-TwFAw.QXycjM1wSN3kjNzEzW}

```
## Flag
pwn.college{oHwFR2zDu--ybI7eeAZdB-TwFAw.QXycjM1wSN3kjNzEzW}

                    
## What I learned
I learned how to check which groups my user belongs to using id, and how to change a file’s group with chgrp so I could gain access. This showed me how Linux file permissions work not just for owners, 
but also for groups, and how I can use that knowledge to read files I otherwise couldn’t.

## 11.4 Changing Permissions
## What I did
```
hacker@permissions~changing-permissions:~$ ls -l
total 36
-rw-r--r-- 1 hacker hacker   4 Sep 28 10:09 COLLEGE
drwxr-xr-x 1 hacker hacker   0 Sep 30 15:48 Desktop
-rw-r--r-- 1 hacker hacker   8 Sep 28 10:53 PWN
-rw-r--r-- 1 hacker hacker 289 Sep 21 14:32 home-backup.tar.gz
-rw-r--r-- 1 hacker hacker 829 Sep 28 10:45 instructions
-rw-r--r-- 1 hacker hacker  95 Sep 28 10:45 myflag
lrwxrwxrwx 1 hacker hacker   5 Sep 26 17:54 not-the-flag -> /flag
-rw-r--r-- 1 root   hacker  77 Sep 29 14:07 output
-rw-r--r-- 1 hacker hacker   0 Sep 28 10:24 stdout
-rw-r--r-- 1 hacker hacker 437 Sep 28 10:31 the-flag
-rw-r--r-- 1 root   hacker  60 Sep 22 05:20 x
hacker@permissions~changing-permissions:~$ chmod o+r /flag
hacker@permissions~changing-permissions:~$ cat /flag
pwn.college{g6-UgKkdu3EGa18qz3uosPI9M9M.QXzcjM1wSN3kjNzEzW}
```
## Flag
pwn.college{g6-UgKkdu3EGa18qz3uosPI9M9M.QXzcjM1wSN3kjNzEzW}
                    
## What I learned
I learned that file permissions determine who can read, write, or execute a file, and that chmod changes those permissions — 
here I used chmod a+r to add read permission for everyone so I could cat /flag. I also learned there are two common ways to express permissions

## 11.5
## What I did
```

```
## Flag

                    
## What I learned

## 11.6
## What I did
```

```
## Flag

                    
## What I learned

## 11.7
## What I did
```

```
## Flag

                    
## What I learned

## 11.8
## What I did
```

```
## Flag

                    
## What I learned

## 11.9
## What I did
```

```
## Flag

                    
## What I learned
## 11.10
## What I did
```

```
## Flag

                    
## What I learned
