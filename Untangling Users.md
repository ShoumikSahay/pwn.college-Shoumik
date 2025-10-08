# Module 10. Untangling Users
## 10.1 Becoming root with su
## What I did
```
root@users~becoming-root-with-su:/home/hacker# cat /flag
pwn.college{A1Q9kp1-Ar51tYZmweGiD2f4-PQ.QX1UDN1wSN3kjNzEzW}

```
## Flag
pwn.college{A1Q9kp1-Ar51tYZmweGiD2f4-PQ.QX1UDN1wSN3kjNzEzW}
                    
## What I learned
I learned how to operate as root: I used su to become root, inspected /root and a user’s home directory to look for likely files, and ran challenge binaries as root when appropriate to reveal the flag.

## 10.2 Other users with su
## What I did
```
hacker@users~other-users-with-su:~$ su zardus
Password: 
zardus@users~other-users-with-su:/home/hacker$ /challenge/run
Congratulations, you have become Zardus! Here is your flag:
pwn.college{Y-ITAZmxf4Qk10yPrFIjU23KzZ4.QX2UDN1wSN3kjNzEzW}
zardus@users~other-users-with-su:/home/hacker$ 



```
## Flag
pwn.college{Y-ITAZmxf4Qk10yPrFIjU23KzZ4.QX2UDN1wSN3kjNzEzW}
                    
## What I learned
I learned that I can switch to another user with su username if I know their password, and once switched, I can run that user’s programs and
access files they have permission for — in this case, using Zardus’s account to get the flag.

## 10.3 Cracking Passwords
## What I did
```
hacker@users~cracking-passwords:~$ john /challenge/shadow-leak
Created directory: /home/hacker/.john
Loaded 1 password hash (crypt, generic crypt(3) [?/64])
Press 'q' or Ctrl-C to abort, almost any other key for status
0g 0:00:00:10 99% 1/3 0g/s 284.0p/s 284.0c/s 284.0C/s zardus999991915..999991900
aardvark         (zardus)
1g 0:00:00:20 100% 2/3 0.04882g/s 284.3p/s 284.3c/s 284.3C/s Johnson..buzz
Use the "--show" option to display all of the cracked passwords reliably
Session completed
hacker@users~cracking-passwords:~$ jog=hn --show /challenge/shadow-leak
bash: --show: command not found
hacker@users~cracking-passwords:~$ john --show /challenge/shadow-leak
hacker:NO PASSWORD:20357:0:99999:7:::
zardus:aardvark:20369:0:99999:7:::

2 password hashes cracked, 0 left
hacker@users~cracking-passwords:~$ su zardus
Password: 
zardus@users~cracking-passwords:/home/hacker$ /challenge/run
Congratulations, you have become Zardus! Here is your flag:
pwn.college{oDffv3jKPByeL9O9DnnP4vrKG1P.QX3UDN1wSN3kjNzEzW}

```
## Flag
pwn.college{oDffv3jKPByeL9O9DnnP4vrKG1P.QX3UDN1wSN3kjNzEzW}
                    
## What I learned
I learned that leaked /etc/shadow password hashes can be cracked with John the Ripper to recover plaintext passwords. 
I used john --show to reveal zardus’s password (aardvark), then used su zardus to become that user and ran /challenge/run to retrieve the flag.

## 10.4 Using sudo
## What I did
```
hacker@users~using-sudo:~$ sudo
usage: sudo -h | -K | -k | -V
usage: sudo -v [-AknS] [-g group] [-h host] [-p prompt] [-u user]
usage: sudo -l [-AknS] [-g group] [-h host] [-p prompt] [-U user] [-u user] [command]
usage: sudo [-AbEHknPS] [-r role] [-t type] [-C num] [-g group] [-h host] [-p prompt] [-T timeout] [-u user] [VAR=value] [-i|-s] [<command>]
usage: sudo -e [-AknS] [-r role] [-t type] [-C num] [-g group] [-h host] [-p prompt] [-T timeout] [-u user] file ...
hacker@users~using-sudo:~$ sudo cat /flag
pwn.college{UWbum93f8dwHqcurp_E6OAsr5iG.QX4UDN1wSN3kjNzEzW}


```
## Flag
pwn.college{UWbum93f8dwHqcurp_E6OAsr5iG.QX4UDN1wSN3kjNzEzW}
                    
## What I learned
I learned how to inspect and use my sudo privileges: I run sudo to see which commands I’m allowed to execute as root (and whether a password is required), then use sudo to run those allowed commands
