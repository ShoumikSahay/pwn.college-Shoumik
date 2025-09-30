# Shell Variables
## Module 7.1 Printing variabbles
## What I did
```
Connected!                                                                        
hacker@variables~printing-variables:~$ echo $FLAG
pwn.college{A1G19vxzWeEwH-iDNxmYiWCi93Q.QX3UTN0wSN3kjNzEzW}
```
## Flag
pwn.college{A1G19vxzWeEwH-iDNxmYiWCi93Q.QX3UTN0wSN3kjNzEzW}
## What I learned
I learned that shell variables hold values I can print with variable expansion — echo $FLAG substituted $FLAG with its contents and printed the flag.
## Module 7.2 Setting variables
## What I did
```
hacker@variables~setting-variables:~$ PWN=COLLEGE
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{wiJktY88wmhRpr0w3vM4ApocgZ_.QX5UTN0wSN3kjNzEzW}
```
## Flag
pwn.college{wiJktY88wmhRpr0w3vM4ApocgZ_.QX5UTN0wSN3kjNzEzW}
## What I learned
I learned that I set shell variables with VAR=1337 (no spaces around =) 
and without the $ when assigning; the $ is only used to read (expand) the variable (echo $VAR). I also learned that spaces turn the line into a command.
## Module 7.3 Multi word Variables
## What I did
```
hacker@variables~multi-word-variables:~$ PWN="COLLEGE YEAH"
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{QzqUyhrq_swK1YSKVcTjm98bp4F.QXwYTN0wSN3kjNzEzW}
```
## Flag
pwn.college{QzqUyhrq_swK1YSKVcTjm98bp4F.QXwYTN0wSN3kjNzEzW}

## What I learned
I learned that to store multi-word values I must quote them — e.g. PWN="COLLEGE YEAH" — because quotes keep the 
spaces as part of the value; without quotes only the first word would be assigned.

## Module 7.4 Exporting Variables
## What I did
```
hacker@variables~exporting-variables:~$ export PWN=COLLEGE
You've set the PWN variable to the proper value!
hacker@variables~exporting-variables:~$ COLLEGE=PWN
You've set the PWN variable to the proper value!
You've set the COLLEGE variable to the proper value!
hacker@variables~exporting-variables:~$ /challenge/run
CORRECT!
You have exported PWN=COLLEGE and set, but not exported, COLLEGE=PWN. Great 
job! Here is your flag:
pwn.college{sE2K9CRMWgyDDMjO9N5ozQyJslu.QXyYTN0wSN3kjNzEzW}
You've set the PWN variable to the proper value!
You've set the COLLEGE variable to the proper value!
```
## Flag
pwn.college{sE2K9CRMWgyDDMjO9N5ozQyJslu.QXyYTN0wSN3kjNzEzW}

## What I learned
I learned that export makes a variable part of the environment so child 
processes can see it (e.g. export PWN=COLLEGE made /challenge/run see PWN), while a plain assignment like COLLEGE=PWN only sets the variable in my current shell 
and is not visible to children.
## Module 7.5 Printing Exported Variables
## What I did
```
hacker@variables~printing-exported-variables:~$ env
SHELL=/run/dojo/bin/bash
HOSTNAME=variables~printing-exported-variables
PWD=/home/hacker
MANPATH=/run/dojo/share/man:
DOJO_AUTH_TOKEN=a3755f63ddc62362fcccdb4752de366dc8845e5d8cb2dca04ddeb76d46bf1de0
HOME=/home/hacker
LANG=C.UTF-8
FLAG=pwn.college{sVmA-vqfOTlzcagFWw1xrzD1ZnE.QX4UTN0wSN3kjNzEzW}
TERMINFO=/run/dojo/share/terminfo
TERM=xterm-256color
SHLVL=2
LC_CTYPE=C.UTF-8
SSL_CERT_FILE=/run/dojo/etc/ssl/certs/ca-bundle.crt
PATH=/run/challenge/bin:/run/dojo/bin:/root/.cargo/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
DEBIAN_FRONTEND=noninteractive
_=/run/dojo/bin/env

```
## Flag
pwn.college{sVmA-vqfOTlzcagFWw1xrzD1ZnE.QX4UTN0wSN3kjNzEzW}
## What I learned
I learned that env shows the exported environment variables my programs can see; using export VAR puts a shell variable 
into that environment, while a plain VAR=value only lives in my shell.

## Module 7.6 Storing Command Output
## What I did
```
hacker@variables~storing-command-output:~$ PWN=$(/challenge/run)
Congratulations! You have read the flag into the PWN variable. Now print it out 
and submit it!
hacker@variables~storing-command-output:~$ echo $PWN
pwn.college{MsLoD_j2GbmBLlYLfXhePBOomxG.QX1cDN1wSN3kjNzEzW}

```
## Flag
pwn.college{MsLoD_j2GbmBLlYLfXhePBOomxG.QX1cDN1wSN3kjNzEzW}
## What I learned
I learned I can save a command’s output into a variable with VAR=$(command) (no spaces), e.g. PWN=$(/challenge/run), which captures the command’s stdout into PWN so I can echo $PWN later.

## Module 7.7 Reading Input
## What I did
```
hacker@variables~reading-input:~$ read -p "Enter value" PWN
Enter value COLLEGE
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{4MZj9RfPHyPgdwAFs0uMSD372N3.QX4cTN0wSN3kjNzEzW}
```
## Flag
pwn.college{4MZj9RfPHyPgdwAFs0uMSD372N3.QX4cTN0wSN3kjNzEzW}

## What I learned
In this exercise, I learned how to use the read command in the shell to take input from the user. By using read 
-p "Enter value" PWN, I was able to prompt myself for a value and store it in the variable PWN. When I typed COLLEGE, the script recognized my input and displayed the flag.

## Module 7.8 Reading Files
## What I did
```
hacker@variables~reading-files:~$ read PWN < /challenge/read_me
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{MmDxqZNDE60PP_EDyFXBzxLGQW5.QXwIDO0wSN3kjNzEzW}
```
## Flag
pwn.college{MmDxqZNDE60PP_EDyFXBzxLGQW5.QXwIDO0wSN3kjNzEzW}
## What I learned
I learned that I can feed a file’s contents into the shell read builtin using input 
redirection — read PWN < /challenge/read_me reads from the file instead of the keyboard and stores the first line into the PWN variable.
