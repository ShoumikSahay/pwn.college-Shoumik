# Module 3. Comprehending Commands
## 3.1 cat, not the pet, the command
## What I did
hacker@commands~cat-not-the-pet-but-the-command:~$ cat flag

pwn.college{4e5LeSnIHicqU_TR4UsbTf7JGkt.QXxcTN0wSN3kjNzEzW}

## Flag
pwn.college{4e5LeSnIHicqU_TR4UsbTf7JGkt.QXxcTN0wSN3kjNzEzW}

## 3.2 catting absolute paths
## What I did
hacker@commands~catting-absolute-paths:~$ cat /flag

pwn.college{wumuYnFjp_WBKe9hGvXkaYu-pIr.QX5ETO0wSN3kjNzEzW}

## Flag
pwn.college{wumuYnFjp_WBKe9hGvXkaYu-pIr.QX5ETO0wSN3kjNzEzW}

## 3.3 
## What I did

## Flag

## 3.4 Grepping for a needle in a haystack
## What I did
hacker@commands~grepping-for-a-needle-in-a-haystack:~$ grep pwn.college /challenge/data.txt

pwn.college{8cxuGsBDPNulY0QklfCfxuoSzPN.QX3EDO0wSN3kjNzEzW}
## Flag
pwn.college{8cxuGsBDPNulY0QklfCfxuoSzPN.QX3EDO0wSN3kjNzEzW}

## 3.5 Comparing files
## What I did
hacker@commands~comparing-files:~$ cat /challenge/decoys_only.txt

hacker@commands~comparing-files:~$ cat /challenge/decoys_and_real.txt

hacker@commands~comparing-files:~$ diff /challenge/decoys_only.txt /challenge/decoys_and_real.txt

9a10

> pwn.college{Qv444fmPD1kpb5sCaWQb7fws5HF.01MwMDOxwSN3kjNzEzW}


## Flag
pwn.college{Qv444fmPD1kpb5sCaWQb7fws5HF.01MwMDOxwSN3kjNzEzW}

## 3.6 Comparing files
## What I did


## Flag

## 3.7 Touching Files
## What I did
hacker@commands~touching-files:~$ touch /tmp/pwn

touch /tmp/college

/challenge/run

Success! Here is your flag:

pwn.college{UqeSU_E7SN9VSUusgw810-lPkcl.QXwMDO0wSN3kjNzEzW}

## Flag
pwn.college{UqeSU_E7SN9VSUusgw810-lPkcl.QXwMDO0wSN3kjNzEzW}

## 3.8 Removing Files
## What I did
hacker@commands~removing-files:~$ rm delete_me

hacker@commands~removing-files:~$ /challenge/check

Excellent removal. Here is your reward:

pwn.college{0p2i9m3FnUF7vhVQAYxRaA-DHTa.QX2kDM1wSN3kjNzEzW}
## Flag
pwn.college{0p2i9m3FnUF7vhVQAYxRaA-DHTa.QX2kDM1wSN3kjNzEzW}

## 3.9 Removing Files
## What I did
hacker@commands~moving-files:~$ mv /flag /tmp/hack-the-planet 

Correct! Performing 'mv /flag /tmp/hack-the-planet'.

hacker@commands~moving-files:~$ /challenge/check

Congrats! You successfully moved the flag to /tmp/hack-the-planet! Here it is:

pwn.college{QO4lcInw99hkJxZrIW8pXemnTKn.0VOxEzNxwSN3kjNzEzW}
## Flag
pwn.college{QO4lcInw99hkJxZrIW8pXemnTKn.0VOxEzNxwSN3kjNzEzW}

## 3.10 Hidden Files
## What I did
hacker@commands~hidden-files:~$ cd /

hacker@commands~hidden-files:/$ ls -a

.  ..  .dockerenv  .flag-22874127188789  bin  boot  challenge  dev  etc  home  lib  lib32  lib64  libx32  media  mnt  nix  opt  proc  root  run  sbin  srv  sys  tmp  usr  var

hacker@commands~hidden-files:/$ grep pwn.college /.flag-22874127188789

pwn.college{ItRGbbbTMpmclunGiaWAgS5LQmC.QXwUDO0wSN3kjNzEzW}

## Flag
pwn.college{ItRGbbbTMpmclunGiaWAgS5LQmC.QXwUDO0wSN3kjNzEzW}

## 3.11 Hidden Files
## What I did
hacker@commands~hidden-files:~$ cd /

hacker@commands~hidden-files:/$ ls -a

.  ..  .dockerenv  .flag-22874127188789  bin  boot  challenge  dev  etc  home  lib  lib32  lib64  libx32  media  mnt  nix  opt  proc  root  run  sbin  srv  sys  tmp  usr  var

hacker@commands~hidden-files:/$ grep pwn.college /.flag-22874127188789

pwn.college{ItRGbbbTMpmclunGiaWAgS5LQmC.QXwUDO0wSN3kjNzEzW}

## Flag
pwn.college{ItRGbbbTMpmclunGiaWAgS5LQmC.QXwUDO0wSN3kjNzEzW}
