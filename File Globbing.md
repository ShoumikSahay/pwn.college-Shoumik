# File Globbing
## Module 5.1 Matching with *
## What I did
```
hacker@globbing~matching-with-:~$ cd /ch*
hacker@globbing~matching-with-:/challenge$ /challenge/run
You ran me with the working directory of /challenge! Here is your flag:
pwn.college{MAHdxNMjIb5UzhCacE7ohHXgdJx.QXxIDO0wSN3kjNzEzW}

```
## Flag
pwn.college{MAHdxNMjIb5UzhCacE7ohHXgdJx.QXxIDO0wSN3kjNzEzW}

## What I learned
I learned how to use globbing in the shell to shorten paths and match directory or file names. 
Instead of typing out the full path /challenge, I used /ch*, and the shell expanded it to the correct directory.

## Module 5.2 Matching with ?
## What I did
```
hacker@globbing~matching-with-:~$ cd /?ha??enge
hacker@globbing~matching-with-:/challenge$ /challenge/run
You ran me with the working directory of /challenge! Here is your flag:
pwn.college{gJaVx-0WexTFt7nEM592U_UBURY.QXyIDO0wSN3kjNzEzW}

```
## Flag
pwn.college{gJaVx-0WexTFt7nEM592U_UBURY.QXyIDO0wSN3kjNzEzW}

## What I learned
hacker@globbing~matching-with-:~$ cd /?ha??enge
hacker@globbing~matching-with-:/challenge$ /challenge/run
You ran me with the working directory of /challenge! Here is your flag:
pwn.college{gJaVx-0WexTFt7nEM592U_UBURY.QXyIDO0wSN3kjNzEzW}

## Module 5.3 Matching with []
## What I did
```
hacker@globbing~matching-with-:~$ cd /challenge/files
hacker@globbing~matching-with-:/challenge/files$ /challenge/run file_[bash]
You got it! Here is your flag!
pwn.college{sR9dWwII9PzSKSo7ffjPDgjoEp8.QXzIDO0wSN3kjNzEzW}

```
## Flag
pwn.college{sR9dWwII9PzSKSo7ffjPDgjoEp8.QXzIDO0wSN3kjNzEzW}

## What I learned
I learned that using character-class globbing like file_[bash] lets me match filenames with a single character from the set. 
The shell expands the pattern, allowing me to pass the correct file to /challenge/run and get the flag.

## Module 5.4 Matching paths with []
## What I did
```


```
## Flag


## What I learned
