# Module 3. Comprehending Commands
## 3.1 cat, not the pet, the command
## What I did
```
hacker@commands~cat-not-the-pet-but-the-command:~$ cat flag

pwn.college{4e5LeSnIHicqU_TR4UsbTf7JGkt.QXxcTN0wSN3kjNzEzW}
```
## Flag
pwn.college{4e5LeSnIHicqU_TR4UsbTf7JGkt.QXxcTN0wSN3kjNzEzW}
## What I learned
I learned how to use cat to read file contents directly from the shell and identify flags when files are readable. This reinforced the importance of simple, direct file inspection for quickly extracting information.

## 3.2 catting absolute paths
## What I did
```
hacker@commands~catting-absolute-paths:~$ cat /flag

pwn.college{wumuYnFjp_WBKe9hGvXkaYu-pIr.QX5ETO0wSN3kjNzEzW}
```
## Flag
pwn.college{wumuYnFjp_WBKe9hGvXkaYu-pIr.QX5ETO0wSN3kjNzEzW}

## What I learned
I learned that using absolute paths (e.g., cat /flag) lets you read files without changing directories, which is especially useful for accessing files in system locations and avoiding context switches.

## 3.3 
## What I did
## Flag

## 3.4 Grepping for a needle in a haystack
## What I did
```
hacker@commands~grepping-for-a-needle-in-a-haystack:~$ grep pwn.college /challenge/data.txt

pwn.college{8cxuGsBDPNulY0QklfCfxuoSzPN.QX3EDO0wSN3kjNzEzW}
```
## Flag
pwn.college{8cxuGsBDPNulY0QklfCfxuoSzPN.QX3EDO0wSN3kjNzEzW}
## What I learned
I learned to use grep to efficiently search large files for patterns (like pwn.college), which dramatically speeds up flag discovery compared with manual scanning.


## 3.5 Comparing files
## What I did
```
hacker@commands~comparing-files:~$ cat /challenge/decoys_only.txt

hacker@commands~comparing-files:~$ cat /challenge/decoys_and_real.txt

hacker@commands~comparing-files:~$ diff /challenge/decoys_only.txt /challenge/decoys_and_real.txt

9a10

> pwn.college{Qv444fmPD1kpb5sCaWQb7fws5HF.01MwMDOxwSN3kjNzEzW}
```
## Flag
pwn.college{Qv444fmPD1kpb5sCaWQb7fws5HF.01MwMDOxwSN3kjNzEzW}

## What I learned
I learned how to use diff to compare two files and spot additions or differences that reveal hidden flags. File comparison is a powerful way to isolate new or changed lines that matter.

## 3.6 Comparing files
## What I did
## Flag

## 3.7 Touching Files
## What I did
```
hacker@commands~touching-files:~$ touch /tmp/pwn

touch /tmp/college

/challenge/run

Success! Here is your flag:

pwn.college{UqeSU_E7SN9VSUusgw810-lPkcl.QXwMDO0wSN3kjNzEzW}
```
## Flag
pwn.college{UqeSU_E7SN9VSUusgw810-lPkcl.QXwMDO0wSN3kjNzEzW}

## What I learned
I practiced creating files with touch and learned how some challenge utilities check for specific filesystem side-effects — creating the right files in the right place can trigger automated success conditions.

## 3.8 Removing Files
## What I did
```
hacker@commands~removing-files:~$ rm delete_me

hacker@commands~removing-files:~$ /challenge/check

Excellent removal. Here is your reward:

pwn.college{0p2i9m3FnUF7vhVQAYxRaA-DHTa.QX2kDM1wSN3kjNzEzW}
```
## Flag
pwn.college{0p2i9m3FnUF7vhVQAYxRaA-DHTa.QX2kDM1wSN3kjNzEzW}
## What I learned
I learned that deleting specific files (with rm) can be part of challenge logic, and that safe, intentional file removal can be used to satisfy checks or unlock rewards — but must be done carefully.

## 3.9 Moving Files
## What I did
```
hacker@commands~moving-files:~$ mv /flag /tmp/hack-the-planet 

Correct! Performing 'mv /flag /tmp/hack-the-planet'.

hacker@commands~moving-files:~$ /challenge/check

Congrats! You successfully moved the flag to /tmp/hack-the-planet! Here it is:

pwn.college{QO4lcInw99hkJxZrIW8pXemnTKn.0VOxEzNxwSN3kjNzEzW}
```
## Flag
pwn.college{QO4lcInw99hkJxZrIW8pXemnTKn.0VOxEzNxwSN3kjNzEzW}

## What I learned
I learned how mv can be used to relocate important files (like mv /flag /tmp/hack-the-planet) to places where they’re readable, and that moving files is a legitimate technique for completing certain tasks.

## 3.10 Hidden Files
## What I did
```
hacker@commands~hidden-files:~$ cd /

hacker@commands~hidden-files:/$ ls -a

.  ..  .dockerenv  .flag-22874127188789  bin  boot  challenge  dev  etc  home  lib  lib32  lib64  libx32  media  mnt  nix  opt  proc  root  run  sbin  srv  sys  tmp  usr  var

hacker@commands~hidden-files:/$ grep pwn.college /.flag-22874127188789

pwn.college{ItRGbbbTMpmclunGiaWAgS5LQmC.QXwUDO0wSN3kjNzEzW}
```

## Flag
pwn.college{ItRGbbbTMpmclunGiaWAgS5LQmC.QXwUDO0wSN3kjNzEzW}
## What I learned
I learned to look for dotfiles and other hidden entries with ls -a and to search them (e.g., grep pwn.college /.flag-...) — hidden files often contain secrets or clues that normal ls hides.



## 3.11 An epic fliesystem quest
## What I did
```
hacker@commands~an-epic-filesystem-quest:/$ cd /

hacker@commands~an-epic-filesystem-quest:/$ ls

DOSSIER  bin  boot  challenge  dev  etc  flag  home  lib  lib32  lib64  libx32  media  mnt  nix  opt  proc  root  run  sbin  srv  sys  tmp  usr  var

hacker@commands~an-epic-filesystem-quest:/$ ls DOSSIER

DOSSIER

hacker@commands~an-epic-filesystem-quest:/$ ls challenge

DESCRIPTION.md

hacker@commands~an-epic-filesystem-quest:/$ cat /challenge/DESCRIPTION.md

hacker@commands~an-epic-filesystem-quest:/$ ls -la /DOSSIER

file /DOSSIER

-rw-r--r-- 1 root root 228 Sep 26 12:58 /DOSSIER

/DOSSIER: ASCII text

hacker@commands~an-epic-filesystem-quest:/$ cat /DOSSIER

Congratulations, you found the clue!

The next clue is in: /opt/linux/linux-5.4/arch/arm/common

hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/arch/arm/common$ cat /opt/linux/linux-5.4/arch/arm/common/.CUE

Tubular find!

The next clue is in: /usr/local/lib/python3.8/dist-packages/anyio

hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/arch/arm/common$ cat /usr/local/lib/python3.8/dist-packages/anyio/BRIEF-TRAPPED

Great sleuthing!

The next clue is in: /usr/share/javascript/mathjax/jax/output/SVG/fonts/STIX-Web/Variants/Italic

The next clue is **delayed** --- it will not become readable until you enter the directory with 'cd'.

hacker@commands~an-epic-filesystem-quest:/usr/lib/python3/dist-packages/networkx/classes/tests/__pycache__$ cd /opt/linux/linux-5.4/Documentation/devicetree/bindings/input/rmi4

hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/Documentation/devicetree/bindings/input/rmi4$ ls

NUGGET  rmi_2d_sensor.txt  rmi_f01.txt  rmi_i2c.txt  rmi_spi.txt

hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/Documentation/devicetree/bindings/input/rmi4$ cat NUGGET

CONGRATULATIONS! Your perserverence has paid off, and you have found the flag!

It is: pwn.college{c7qxp6vkSBDG8Nm9S9K49plynGs.QX5IDO0wSN3kjNzEzW}
```


## Flag
pwn.college{c7qxp6vkSBDG8Nm9S9K49plynGs.QX5IDO0wSN3kjNzEzW}

## What I learnt
Through this challenge, I gained practical experience navigating the Linux filesystem using commands like cd, ls, and cat. I learned how to locate and read hidden files (dotfiles) using ls -a, and understood how file permissions and ownership affect access. The challenge also taught me to carefully read clues and use absolute paths to avoid traps, reinforcing the importance of precision in command-line operations.

## 3.12 Making Directories
## What I did
```
hacker@commands~making-directories:~$ mkdir /tmp/pwn
hacker@commands~making-directories:~$ cd /tmp/pwn
hacker@commands~making-directories:/tmp/pwn$ touch college
hacker@commands~making-directories:/tmp/pwn$ /challenge/run
Success! Here is your flag:
pwn.college{04egtmiyE5wSdW6iOpjxgp86CI3.QXxMDO0wSN3kjNzEzW}
```
## Flag
pwn.college{04egtmiyE5wSdW6iOpjxgp86CI3.QXxMDO0wSN3kjNzEzW}
## What I learned
I learned the process of making a directory using mkdir command, and then subsequently creating files in the directory.

## 3.12 Making Directories
## What I did
```
hacker@commands~making-directories:~$ mkdir /tmp/pwn
hacker@commands~making-directories:~$ cd /tmp/pwn
hacker@commands~making-directories:/tmp/pwn$ touch college
hacker@commands~making-directories:/tmp/pwn$ /challenge/run
Success! Here is your flag:
pwn.college{04egtmiyE5wSdW6iOpjxgp86CI3.QXxMDO0wSN3kjNzEzW}
```
## Flag
pwn.college{04egtmiyE5wSdW6iOpjxgp86CI3.QXxMDO0wSN3kjNzEzW}
## What I learned
I learned the process of making a directory using mkdir command, and then subsequently creating files in the directory.

## 3.13 Finding Files
## What I did
```
hacker@commands~finding-files:~$ find . -name file
hacker@commands~finding-files:~$ find / -type f -name flag 2>/dev/null
/usr/share/racket/pkgs/scribble-lib/scribble/acmart/flag
hacker@commands~finding-files:~$ cat /usr/share/racket/pkgs/scribble-lib/scribble/acmart/flag 2>/dev/null
pwn.college{MrAtCABB9KPQQSwGeD2bEra0Z4r.QXyMDO0wSN3kjNzEzW}
```
## Flag
pwn.college{MrAtCABB9KPQQSwGeD2bEra0Z4r.QXyMDO0wSN3kjNzEzW}
## What I learned
In this challenge, I learned how to use the find command to search for files in the Linux filesystem. I understood that find allows filtering by name, type, and location, and that it’s useful for locating hidden or scattered files such as the flag

## 3.14 Linking Files
## What I did
```
hacker@commands~linking-files:~$ ln -s /flag /home/hacker/not-the-flag
ln: failed to create symbolic link '/home/hacker/not-the-flag': File exists
hacker@commands~linking-files:~$ /challenge/catflag
About to read out the /home/hacker/not-the-flag file!
pwn.college{k-v5g6lANxBhe0hQO02mRGkvRLu.QX5ETN1wSN3kjNzEzW}
```
## Flag
pwn.college{k-v5g6lANxBhe0hQO02mRGkvRLu.QX5ETN1wSN3kjNzEzW}

## What I learned
Through this level, I learned how symbolic links work and how they can be used to redirect file access. I practiced creating symlinks with ln -s.



