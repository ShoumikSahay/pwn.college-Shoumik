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

## 13.3
## What I did
```

```
## Flag

## What I learned

## 13.4
## What I did
```

```
## Flag

## What I learned

## 13.5
## What I did
```

```
## Flag

## What I learned

## 13.6
## What I did
```

```
## Flag

## What I learned



## What I learned
