# Module 9. Processes and Jobs
## 9.1 Listing Processes
## What I did
```
hacker@processes~listing-processes:~$ ps -ef
UID          PID    PPID  C STIME TTY          TIME CMD
root           1       0  0 08:45 ?        00:00:00 /sbin/docker-init -- /nix/var/nix/profiles/dojo-workspace/bin/dojo-init /run/dojo/bin/sleep 6h
root           7       1  0 08:45 ?        00:00:00 /run/dojo/bin/sleep 6h
root         132       1  0 08:45 ?        00:00:00 /challenge/29767-run-28773
root         135     132  0 08:45 ?        00:00:00 sleep 6h
hacker       137       0  0 08:45 pts/0    00:00:00 /nix/store/0nxvi9r5ymdlr2p24rjj9qzyms72zld1-bash-interactive-5.2p37/bin/bash /run/dojo/bin/ssh-entrypoint
hacker       143     137  0 08:45 pts/0    00:00:00 /run/dojo/bin/bash --login
hacker       152     143  0 08:45 pts/0    00:00:00 ps -ef
hacker@processes~listing-processes:~$ /challenge/29767-run-28773
Yahaha, you found me! Here is your flag:
pwn.college{4qReekKSuX3FlbDaan_b0LU2o0T.QX4MDO0wSN3kjNzEzW}

```
## Flag
pwn.college{4qReekKSuX3FlbDaan_b0LU2o0T.QX4MDO0wSN3kjNzEzW}
                    
## What I learned
I learned how to list running processes with ps -ef, read the output to find a suspicious challenge process, and execute that process to retrieve the flag.
Using ps helped me locate the program by PID/command so I could run /challenge/29767-run-28773 and reveal the flag.

## 9.2
## What I did
```

```
## Flag

## What I learned

## 9.3 Interrupting Processes
## What I did
```
hacker@processes~interrupting-processes:~$ /challenge/run
I could give you the flag... but I won't, until this process exits. Remember, 
you can force me to exit with Ctrl-C. Try it now!
^C
Good job! You have used Ctrl-C to interrupt this process! Here is your flag:
pwn.college{Y_xW_clWVg71UFzX8CgYPfT3_Gx.QXzQDO0wSN3kjNzEzW}
```
## Flag
pwn.college{Y_xW_clWVg71UFzX8CgYPfT3_Gx.QXzQDO0wSN3kjNzEzW}
## What I learned
I learned that I can interrupt a running process in the terminal using Ctrl-C. This sends a SIGINT signal, telling the process to stop immediately. 
It’s a quick way to regain control of the terminal or stop a command that is waiting or running indefinitely.

## 9.4 Killing Misbehaving Processes
## What I did
```
hacker@processes~killing-misbehaving-processes:~$ /challenge/run | ps -e
    PID TTY          TIME CMD
      1 ?        00:00:00 docker-init
      7 ?        00:00:00 /run/dojo/bin/s
    139 ?        00:00:00 .init
    140 ?        00:00:00 .init
    141 ?        00:00:00 su
    142 ?        00:00:00 sleep
    143 ?        00:00:00 sleep
    144 ?        00:00:00 decoy
    146 pts/0    00:00:00 ssh-entrypoint
    152 pts/1    00:00:00 ssh-entrypoint
    158 pts/0    00:00:00 bash
    159 pts/1    00:00:00 bash
    177 pts/1    00:00:00 bash
    178 pts/1    00:00:00 ps
hacker@processes~killing-misbehaving-processes:~$ kill 144
hacker@processes~killing-misbehaving-processes:~$ /challenge/run
Sending the flag to /tmp/flag_fifo!

```
## Flag
pwn.college{IZR-ipXuByHzTMqXFvgdtrYmrtC.0FNzMDOxwSN3kjNzEzW}
## What I learned
I learned how to identify and terminate a misbehaving process that was blocking a resource — in this case, a named pipe (FIFO). By using commands like ps, lsof, and kill, I could find which process was holding the FIFO and stop it so that /challenge/run could successfully send the flag through. 
This taught me how to manage processes that interfere with system resources.

## 9.5 Suspending processes
## What I did
```
hacker@processes~suspending-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running in 
this terminal... Let's check!

UID          PID    PPID  C STIME TTY          TIME CMD
root         145     129  0 10:29 pts/0    00:00:00 bash /challenge/run
root         147     145  0 10:29 pts/0    00:00:00 ps -f

I don't see a second me!

To pass this level, you need to suspend me and launch me again! You can 
background me with Ctrl-Z or, if you're not ready to do that for whatever 
reason, just hit Enter and I'll exit!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~suspending-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running in 
this terminal... Let's check!

UID          PID    PPID  C STIME TTY          TIME CMD
root         145     129  0 10:29 pts/0    00:00:00 bash /challenge/run
root         152     129  0 10:29 pts/0    00:00:00 bash /challenge/run
root         154     152  0 10:29 pts/0    00:00:00 ps -f

Yay, I found another version of me! Here is the flag:
pwn.college{YTzzmYDABRedvMDHfIubhxt2CVO.QX1QDO0wSN3kjNzEzW}
```
## Flag
pwn.college{YTzzmYDABRedvMDHfIubhxt2CVO.QX1QDO0wSN3kjNzEzW}
## What I learned
I learned how to suspend a running process using Ctrl-Z. This sends a SIGTSTP signal, pausing the process and placing it in the background instead of killing it.
It taught me how to temporarily stop a program to free up the terminal for other commands, without ending the process completely.

## 9.6 Resuming Processes
## What I did
```
Connected!                                                                        
hacker@processes~resuming-processes:~$ /challenge/run
Let's practice resuming processes! Suspend me with Ctrl-Z, then resume me with 
the 'fg' command! Or just press Enter to quit me!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~resuming-processes:~$ fg
/challenge/run
I'm back! Here's your flag:
pwn.college{s7-eqFE2OajLAYNmtEeMMVPOHa6.QX2QDO0wSN3kjNzEzW}
Don't forget to press Enter to quit me!

```
## Flag
pwn.college{s7-eqFE2OajLAYNmtEeMMVPOHa6.QX2QDO0wSN3kjNzEzW}
## What I learned
I learned how to resume a suspended process using the fg command. After pausing a program with Ctrl-Z, 
I can use fg to bring it back to the foreground and let it continue running. This taught me how to manage background and foreground jobs in the terminal effectively.

## 9.7 Backgrounding Processes
## What I did
```
hacker@processes~backgrounding-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running *and 
not suspended* in this terminal... Let's check!

UID          PID STAT CMD
root         138 S+   bash /challenge/run
root         140 R+   ps -o user=UID,pid,stat,cmd

I don't see a second me!

To pass this level, you need to suspend me, resume the suspended process in the 
background, and then launch a new version of me! You can background me with 
Ctrl-Z (and resume me in the background with 'bg') or, if you're not ready to 
do that for whatever reason, just hit Enter and I'll exit!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~backgrounding-processes:~$ bg
[1]+ /challenge/run &
hacker@processes~backgrounding-processes:~$ 


Yay, I'm now running the background! Because of that, this text will probably 
overlap weirdly with the shell prompt. Don't panic; just hit Enter a few times 
to scroll this text out.

hacker@processes~backgrounding-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running *and 
not suspended* in this terminal... Let's check!

UID          PID STAT CMD
root         138 S    bash /challenge/run
root         148 S    sleep 6h
root         149 S+   bash /challenge/run
root         151 R+   ps -o user=UID,pid,stat,cmd

Yay, I found another version of me running in the background! Here is the flag:
pwn.college{A3Jw5jTVbEG-a7PggObkaKMzdhz.QX3QDO0wSN3kjNzEzW}
```
## Flag
pwn.college{A3Jw5jTVbEG-a7PggObkaKMzdhz.QX3QDO0wSN3kjNzEzW}
## What I learned
I learned how to resume a suspended process in the background using the bg command. This lets a program keep running without blocking the terminal, 
allowing me to run other commands simultaneously — a key skill for multitasking in Linux.

## 9.8 Foregrounding processes
## What I did
```
hacker@processes~foregrounding-processes:~$ /challenge/run
To pass this level, you need to suspend me, resume the suspended process in the 
background, and *then* foreground it without re-suspending it! You can 
background me with Ctrl-Z (and resume me in the background with 'bg') or, if 
you're not ready to do that for whatever reason, just hit Enter and I'll exit!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~foregrounding-processes:~$ bg
[1]+ /challenge/run &
hacker@processes~foregrounding-processes:~$ 


Yay, I'm now running the background! Because of that, this text will probably 
overlap weirdly with the shell prompt. Don't panic; just hit Enter a few times 
to scroll this text out. After that, resume me into the foreground with 'fg'; 
I'll wait.

hacker@processes~foregrounding-processes:~$ fg
/challenge/run
YES! Great job! I'm now running in the foreground. Hit Enter for your flag!

pwn.college{YneDByeQbDs1wQJHF0A_la4YJQ2.QX4QDO0wSN3kjNzEzW}
```
## Flag
pwn.college{YneDByeQbDs1wQJHF0A_la4YJQ2.QX4QDO0wSN3kjNzEzW}
## What I learned
I learned how to move a background process back to the foreground using the fg command. After suspending a process with Ctrl-Z and resuming it in the background using bg, I can bring it back to the foreground with fg to interact with it again. 
This taught me how to fully control process states — switching between foreground and background as needed.

## 9.9 Starting Backgrounded Processes
## What I did
```
hacker@processes~starting-backgrounded-processes:~$ /challenge/run&
[1] 138
hacker@processes~starting-backgrounded-processes:~$ 


Yay, you started me in the background! Because of that, this text will probably 
overlap weirdly with the shell prompt, but you're used to that by now...

Anyways! Here is your flag!
pwn.college{sw4fDmyOAeRZmacO0nifAz63Lwk.QX5QDO0wSN3kjNzEzW}


```
## Flag
pwn.college{sw4fDmyOAeRZmacO0nifAz63Lwk.QX5QDO0wSN3kjNzEzW}
## What I learned
I learned how to start a process directly in the background by appending & to the command. This allows the program to 
run while freeing up the terminal for other commands — a key concept for multitasking in Linux.

## 9.10 Process Exit codes
## What I did
```
hacker@processes~process-exit-codes:~$ /challenge/get-code
Exiting with an error code!
hacker@processes~process-exit-codes:~$ echo $?
109
hacker@processes~process-exit-codes:~$ /challenge/submit-code 109
CORRECT! Here is your flag:
pwn.college{o3RZwLaxSCROkh7mTrj5nLCiSro.QX5YDO1wSN3kjNzEzW}
```
## Flag
pwn.college{o3RZwLaxSCROkh7mTrj5nLCiSro.QX5YDO1wSN3kjNzEzW}
## What I learned
I learned how to capture a program’s exit code using $? immediately after it runs and then use that code as an argument for another command. 
This taught me how processes communicate success or failure through exit codes and how to chain commands based on those results.

