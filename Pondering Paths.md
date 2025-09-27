# Module 2. Pondering Paths
## 2.1 The Root
## What I did
```
hacker@paths~the-root:~$ /pwn

BOOM!!!

Here is your flag:

pwn.college{YIlFIXE0gZJYcIzN-W50IwqSVO-.QX4cTO0wSN3kjNzEzW}
```

## Flag
pwn.college{YIlFIXE0gZJYcIzN-W50IwqSVO-.QX4cTO0wSN3kjNzEzW}
## What I learned
I learned that executing a program by absolute path (starting with /) runs it directly from the filesystem root. This taught me to be confident invoking commands with full paths when I want to be explicit about which program I’m running.
## 2.2 Program and absolute paths
## What I did
hacker@paths~program-and-absolute-paths:~$ /challenge/run

Correct!!!

/challenge/run is an absolute path! Here is your flag:

pwn.college{IEWveuuzUTIZK3VZr5H31gaow9y.QX1QTN0wSN3kjNzEzW}


## Flag
pwn.college{IEWveuuzUTIZK3VZr5H31gaow9y.QX1QTN0wSN3kjNzEzW}
## What I learned
I practiced running an executable using its absolute path and saw that it works the same regardless of my current directory. Using absolute paths made the command predictable and removed any ambiguity about which binary was being executed.
## 2.3 Position thy self
## What I did
hacker@paths~position-thy-self:~$ cd /usr/share/doc

hacker@paths~position-thy-self:/usr/share/doc$ /challenge/run

Correct!!!

/challenge/run is an absolute path, invoked from the right directory!

Here is your flag:

pwn.college{AKjU7Pt4uB7aqKMGRCRx2bl0N3t.QX2QTN0wSN3kjNzEzW}

## Flag
pwn.college{AKjU7Pt4uB7aqKMGRCRx2bl0N3t.QX2QTN0wSN3kjNzEzW}
## What I learned
I learned that my current working directory doesn’t matter when I use absolute paths, but it’s still good to be aware of where I am. Running the same absolute command from another location reinforced that absolute invocation is independent of the shell’s cwd.
## 2.4 Position thy self
## What I did
hacker@paths~position-elsewhere:~$ cd /etc

hacker@paths~position-elsewhere:/etc$ /challenge/run

Correct!!!

/challenge/run is an absolute path, invoked from the right directory!

Here is your flag:

pwn.college{8uRRM_U_jr4hF_IshIQaT7BSlNE.QX3QTN0wSN3kjNzEzW}

## Flag
pwn.college{8uRRM_U_jr4hF_IshIQaT7BSlNE.QX3QTN0wSN3kjNzEzW}
## What I learned
I reinforced the previous lesson: absolute paths always point to the same file no matter where I run them from. Being explicit about paths helps avoid mistakes when multiple programs or copies might exist.


## 2.5 Position yet elsewhere
## What I did
hacker@paths~position-yet-elsewhere:~$ /challenge/run 

Incorrect...

You are not currently in the /proc/132/fd directory.

Please use the `cd` utility to change directory appropriately.

hacker@paths~position-yet-elsewhere:~$ cd /proc/132/fd

hacker@paths~position-yet-elsewhere:/proc/132/fd$ /challenge/run

Correct!!!

/challenge/run is an absolute path, invoked from the right directory!

Here is your flag:

pwn.college{039nNIWpq23_9ysG1uI-rnQqFLj.QX4QTN0wSN3kjNzEzW}
## Flag
pwn.college{039nNIWpq23_9ysG1uI-rnQqFLj.QX4QTN0wSN3kjNzEzW}
## What I learned
## 2.6 Implicit relative paths, from /
## What I did
hacker@paths~implicit-relative-paths-from-:/$ challenge/run

Correct!!!

challenge/run is a relative path, invoked from the right directory!

Here is your flag:

pwn.college{U31m1zSOaCp6VJ3SN6JzWJJi4Zm.QX5QTN0wSN3kjNzEzW}
## Flag
pwn.college{U31m1zSOaCp6VJ3SN6JzWJJi4Zm.QX5QTN0wSN3kjNzEzW}
## What I learned
## 2.7 Explicit relative paths, from /
## What I did
hacker@paths~explicit-relative-paths-from-:~$ cd /

hacker@paths~explicit-relative-paths-from-:/$ ./challenge/run

Correct!!!

./challenge/run is a relative path, invoked from the right directory!

Here is your flag:

pwn.college{4guq6ndeXbb6TWevl_Mw44ww-9R.QXwUTN0wSN3kjNzEzW}
## Flag
pwn.college{4guq6ndeXbb6TWevl_Mw44ww-9R.QXwUTN0wSN3kjNzEzW}
## What I learned
## 2.8 Impicit relative paths
## What I did
hacker@paths~implicit-relative-path:/run/challenge$ cd /challenge

hacker@paths~implicit-relative-path:/challenge$ ./run

Correct!!!

./run is a relative path, invoked from the right directory!

Here is your flag:

pwn.college{EY5COx12vQxbhwEg7sNbKcHmgEE.QXxUTN0wSN3kjNzEzW}

## Flag
pwn.college{EY5COx12vQxbhwEg7sNbKcHmgEE.QXxUTN0wSN3kjNzEzW}
## What I learned
## 2.9 Home sweet Home
## What I did
hacker@paths~home-sweet-home:/home$ cd ~

hacker@paths~home-sweet-home:~$ /challenge/run ~/x

Writing the file to /home/hacker/x!

... and reading it back to you:

pwn.college{M_ja7hXCy1W1mrUnIMffLSDmpHZ.QXzMDO0wSN3kjNzEzW}

## Flag
pwn.college{M_ja7hXCy1W1mrUnIMffLSDmpHZ.QXzMDO0wSN3kjNzEzW}

## What I learned


