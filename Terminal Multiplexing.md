# Module 13. Terminal Multiplexing
## 13.1 Launching Screens
## What I did
```
Congratulations! You're inside a screen session!
Here's your flag:
pwn.college{wjwLYBi7L4OZ3RQiqVZuzO_pq8U.0VN4IDOxwSN3kjNzEzW}
hacker@terminal-multiplexing~launching-screen:~$

```
## Flag
pwn.college{wjwLYBi7L4OZ3RQiqVZuzO_pq8U.0VN4IDOxwSN3kjNzEzW}
## What I learned
I learned how to launch a screen in a terminal using the screen command.

## 13.2 Detatching and attatching
## What I did
```
hacker@terminal-multiplexing~launching-screen:~$ screen
[detached from 140.pts-0.terminal-multiplexing~detaching-and-attaching]
hacker@terminal-multiplexing~detaching-and-attaching:~$ /challenge/run
Found detached screen session: 140.pts-0.terminal-multiplexing~detaching-and-attaching
Sending flag to your screen session...

Flag sent! Now reattach to your screen session with:

  screen -r

You'll find the flag waiting for you there!
hacker@terminal-multiplexing~detaching-and-attaching:~$ screen -r
[screen is terminating]

hacker@terminal-multiplexing~detaching-and-attaching:~$ echo Yes! Flag is: pwn.college{sBO9mpv6QBHbTk2BCewaftV1AJq.0lN4IDOxwSN3kjNzEzW}
Yes! Flag is: pwn.college{sBO9mpv6QBHbTk2BCewaftV1AJq.0lN4IDOxwSN3kjNzEzW}
```
## Flag
pwn.college{sBO9mpv6QBHbTk2BCewaftV1AJq.0lN4IDOxwSN3kjNzEzW}
## What I learned
I used screen to create a detached terminal session, ran /challenge/run which detected the detached session and sent the flag into it, and then reattached
with screen -r to retrieve the flag. I learned how terminal multiplexers let processes write to background sessions, how /challenge/run can target an existing screen, 
and that reattaching displays whatever was sent (even if the session later terminates).

## 13.3 Finding Sessions
## What I did
```
hacker@terminal-multiplexing~finding-sessions:~$ screen -ls
There are screens on:
	150.pts-0.terminal-multiplexing~launching-screen	(Remote or dead)
	144.session_ef101927e79b98cd	(Detached)
	147.session_9f6f8a70bb402f20	(Detached)
	150.session_69503a890a5ca062	(Detached)
4 Sockets in /home/hacker/.screen.
hacker@terminal-multiplexing~finding-sessions:~$ screen -r 144
[detached from 144.session_ef101927e79b98cd]
hacker@terminal-multiplexing~finding-sessions:~$ screen -r 147
[detached from 147.session_9f6f8a70bb402f20]
```
## Flag
pwn.college{MT41KwY4-04iDiQwjoOKbNEemvC.01N4IDOxwSN3kjNzEzW}
## What I learned
I listed running screen sessions with screen -ls and learned to read their states. I reattached specific sessions with screen -r <id> and saw messages like [detached from ...], which taught me that attaching a session can detach it from another terminal.

## 13.4 Switching Windows
## What I did
```
Excellent work! You found window 0!
Here is your flag: pwn.college{ovFGzn1n5KKrFcJS8ZFCwqU73lS.0FO4IDOxwSN3kjNzEzW}
hacker@terminal-multiplexing~switching-windows:~$ cat /challenge/run       
```
## Flag
pwn.college{ovFGzn1n5KKrFcJS8ZFCwqU73lS.0FO4IDOxwSN3kjNzEzW}
## What I learned
I learned that a single screen session can hold multiple windows (like tabs) and that I can create and navigate them with Ctrl-A shortcuts — Ctrl-A c to create, Ctrl-A n / Ctrl-A p to move next/previous, Ctrl-A 0–Ctrl-A 9 to jump to a numbered window, or Ctrl-A " to pick from a menu.

## 13.5 Attaching and detaching(tmux)
## What I did
```
hacker@terminal-multiplexing~detaching-and-attaching-tmux:~$ tmux attatch
unknown command: attatch
hacker@terminal-multiplexing~detaching-and-attaching-tmux:~$ tmux
[detached (from session 1)]
hacker@terminal-multiplexing~detaching-and-attaching-tmux:~$ /challenge/run
Found detached tmux session: 0
Sending flag to your tmux session...

Flag sent! Now reattach to your tmux session with:
  tmux attach

You'll find the flag waiting for you there!
hacker@terminal-multiplexing~detaching-and-attaching-tmux:~$  echo Congratulations, here is your flag: pwn.college{IV3WL0s8W1_28TuFQ_thye6Ik6p.0VO4IDOxwSN3kjNzEzW}
Congratulations, here is your flag: pwn.college{IV3WL0s8W1_28TuFQ_thye6Ik6p.0VO4IDOxwSN3kjNzEzW}
```
## Flag
pwn.college{IV3WL0s8W1_28TuFQ_thye6Ik6p.0VO4IDOxwSN3kjNzEzW}
## What I learned
I launched a `tmux` session, learned that `Ctrl-B` is tmux’s command prefix (use `Ctrl-B d` to detach), and that `tmux ls` / `tmux attach` (or `tmux a`) manage sessions. I detached, ran `/challenge/run` which sent the flag into the detached session, then reattached to retrieve the flag — showing how detached tmux sessions can receive output while I’m away.

## 13.6
## What I did
```
Excellent work! You found window 0!
Here is your flag: pwn.college{c4zHQ7uDyTdGIR4gCjwCyhSwngT.0FM5IDOxwSN3kjNzEzW}
hacker@terminal-multiplexing~switching-windows-tmux:~$ 

```
## Flag
pwn.college{c4zHQ7uDyTdGIR4gCjwCyhSwngT.0FM5IDOxwSN3kjNzEzW}
## What I learned

I learned that, like `screen`, a single `tmux` session can have multiple windows. I can switch between them using `Ctrl-B` followed by `n`/`p` for next/previous, or `Ctrl-B` followed by the window number to jump directly. By navigating to Window 0 in the tmux session, I was able to find and retrieve the flag, showing how tmux organizes multiple tasks within one session.



