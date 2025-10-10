# Module 14 PONDERING PATHS
## 14.1 The Path Variable 
## What I did
```
hacker@path~the-path-variable:~$ PATH="" /challenge/run
Trying to remove /flag...
/challenge/run: line 4: rm: No such file or directory
The flag is still there! I might as well give it to you!
pwn.college{gd7wPJ1_ikwXE9n5sc_LTXytNcQ.QX2cDM1wSN3kjNzEzW}
```
## Flag
pwn.college{gd7wPJ1_ikwXE9n5sc_LTXytNcQ.QX2cDM1wSN3kjNzEzW}
## What I learned
From this challenge, I learned how to manipulate the PATH environment variable to control a child process's ability to execute commands. 
I discovered the powerful VAR="value" command syntax, which allowed 
me to temporarily break the PATH for the challenge script so it couldn't find rm, all without affecting my own shell session.

## 14.2 Setting Path
## What I did
```
hacker@path~setting-path:~$ PATH=/challenge/more_commands/
hacker@path~setting-path:~$ /challenge/run
Invoking 'win'....
Congratulations! You properly set the flag and 'win' has launched!
pwn.college{Ip39XLvUmBEOZ1BdRfVnOSN8mSB.QX1cjM1wSN3kjNzEzW}
```
## Flag
pwn.college{Ip39XLvUmBEOZ1BdRfVnOSN8mSB.QX1cjM1wSN3kjNzEzW}
## What I learned
From this challenge, I learned that I can control where the shell searches for commands by directly setting the PATH variable. By replacing the PATH with a new, 
custom directory, I instructed my shell to look for executables only in that specific location. 
This allowed the challenge script to successfully find and invoke the 'win' command, which it couldn't have located in the standard system directories.

## 14.3 Finding Commands
## What I did
```
hacker@path~finding-commands:~$ which win
/challenge/paths/7086/win
hacker@path~finding-commands:~$ cat /challenge/paths/7086
cat: /challenge/paths/7086: Is a directory
hacker@path~finding-commands:~$ /challenge/paths/7086
bash: /challenge/paths/7086: Is a directory
hacker@path~finding-commands:~$ cd /challenge/paths/7086
hacker@path~finding-commands:/challenge/paths/7086$ ls
flag  win
hacker@path~finding-commands:/challenge/paths/7086$ cat flag
pwn.college{YfoM3D52_F94pS-PSroHTPPvD6F.01NzEzNxwSN3kjNzEzW}

```
## Flag
pwn.college{YfoM3D52_F94pS-PSroHTPPvD6F.01NzEzNxwSN3kjNzEzW}

## What I learned
From this challenge, I learned how to use the which command as a powerful tool for locating executables. By running which win, my shell searched all 
the directories in my PATH and revealed the full path to the 'win' program. 
This allowed me to investigate its location, and I discovered that the flag was stored in the same directory. 

## 14.4 Adding Commands
## What I did
```
hacker@path~adding-commands:~$ mkdir ~/my_commands
hacker@path~adding-commands:~$ echo -e '#!/bin/bash\n/bin/cat /flag' > ~/my_commands/win
hacker@path~adding-commands:~$ chmod +x ~/my_commands/win
hacker@path~adding-commands:~$ PATH=~/my_commands /challenge/run
Invoking 'win'....
pwn.college{Ya1S8BJN7p9nrYaG1lFc51tudsx.QX2cjM1wSN3kjNzEzW}

```
## Flag
pwn.college{Ya1S8BJN7p9nrYaG1lFc51tudsx.QX2cjM1wSN3kjNzEzW}
## What I learned
I've learned to take control of my shell environment by creating my own commands as scripts and mastering the PATH variable. 
I now know how to add my own directories (like ~/my_commands) to the PATH so the shell can find my custom tools, just like it 
finds standard programs like ls or cat. I can also use utilities like which to find the absolute path of any command, making my scripts more robust and self-sufficient. 

## 14.5 Hijacking Commands
## What I did
```
hacker@path~hijacking-commands:~$ PATH=~/my_commands:$PATH /challenge/run
Trying to remove /flag...
Found 'rm' command at /home/hacker/my_commands/rm. Executing!
pwn.college{Ec1NywFcgcLW3EfBmdnaPVikZQB.QX3cjM1wSN3kjNzEzW}

```
## Flag
pwn.college{Ec1NywFcgcLW3EfBmdnaPVikZQB.QX3cjM1wSN3kjNzEzW}
## What I learned
From this challenge, I learned a powerful security concept: using PATH hijacking for privilege escalation. By creating my own fake rm script and placing its directory at the front of 
the PATH, I tricked a root-level program into executing my code instead of the real command.
