# Module 1. Hello Hackers
## 1.1 Intro to Commands
## What I did
```
Here, I executed the whoami command, which simply prints the username (hacker) to the terminal.
Further, I invoked the hello command to get the flag.

hacker@dojo:~$ whoami

hacker

hacker@dojo:~$ hello

Success! Here is your flag:

pwn.college{8OPEhEbtzqNcnjvqJObYb_P8xPT.QX3YjM1wSN3kjNzEzW}
```
## Flag
pwn.college{8OPEhEbtzqNcnjvqJObYb_P8xPT.QX3YjM1wSN3kjNzEzW}
## What I learned
I learned how to run basic commands and read their output — for example, whoami showed my current username. I also practiced invoking a simple program (hello) to retrieve the flag, which reinforced how to execute commands from the shell and trust their output.


## 1.2 Intro to Arguments
## What I did
```
In this challenge, to get the flag, I ran the hello command (NOT the echo command) with a single argument of hackers. 

hacker@hello~intro-to-arguments:~$ hello hackers

Success! Here is your flag:

pwn.college{o2qqwxv4ojON6fo2eoW0XEUZaIb.QX4YjM1wSN3kjNzEzW}
```
## Flag
pwn.college{o2qqwxv4ojON6fo2eoW0XEUZaIb.QX4YjM1wSN3kjNzEzW}

## What I learned
I learned that commands can take arguments which change their behavior. By running hello hackers (not echo), I saw how supplying the right argument produces the expected result — a small but crucial lesson in using command-line tools correctly.

## 1.3 Command History
## What I did
```
In this challenge, to get the flag, I shuffled through the history of commands using the up/down arrow keys.
```
## Flag
pwn.college{o2qqwxv4ojON6fo2eoW0XEUZaIb.QX4YjM1wSN3kjNzEzW}
## What I learned
I learned how to navigate my command history with the arrow keys to quickly recall and re-run past commands. This saved time and reduced typing, showing how simple shell features can speed up exploration and troubleshooting.
