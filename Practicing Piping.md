# Practicing Piping
## Module 6.1 Redirecting Output
## What I did
```
hacker@piping~redirecting-output:~$ echo PWN > COLLEGE
Correct! You successfully redirected 'PWN' to the file 'COLLEGE'! Here is your 
flag:
pwn.college{MoZUChPsi6i1_O-g-1-9-k5NTc7.QX0YTN0wSN3kjNzEzW}
```
## Flag
pwn.college{MoZUChPsi6i1_O-g-1-9-k5NTc7.QX0YTN0wSN3kjNzEzW}

## What I learned
I learned how to redirect command output into a file using > — for example echo PWN > COLLEGE created (or replaced) 
the file COLLEGE and wrote PWN into it. This taught me that > sends a command’s standard output to a file (overwriting it), 
and that I can use redirection to capture program output for later use.

## Module 6.2 Redirecting more output
## What I did
```
hacker@piping~redirecting-more-output:~$ /challenge/run > myflag
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : myflag
[INFO] - the challenge will output a reward file if all the tests pass : /flag

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /flag file.

[TEST] You should have redirected my stdout to a file called myflag. Checking...

[PASS] The file at the other end of my stdout looks okay!
[PASS] Success! You have satisfied all execution requirements.
hacker@piping~redirecting-more-output:~$ cat myflag

[FLAG] Here is your flag:
[FLAG] pwn.college{smc94o6HHrt3xerWugYIZNDNIlk.QX1YTN0wSN3kjNzEzW}
```
## Flag
pwn.college{smc94o6HHrt3xerWugYIZNDNIlk.QX1YTN0wSN3kjNzEzW}

## What I learned
learned how to redirect a program’s standard output into a file using >. 
By running /challenge/run > myflag I captured the program’s output in myflag instead of seeing it on the terminal, and then I read that file with cat myflag to get the flag.

## Module 6.3 Appending Output
## What I did
```
hacker@piping~appending-output:~$ /challenge/run > /home/hacker/the-flag
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : /home/hacker/the-flag

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] Good luck!

[TEST] You should have redirected my stdout to a file called /home/hacker/the-flag. Checking...

[HINT] File descriptors are inherited from the parent, unless the FD_CLOEXEC is set by the parent on the file descriptor.
[HINT] For security reasons, some programs, such as python, do this by default in certain cases. Be careful if you are
[HINT] creating and trying to pass in FDs in python.

[PASS] The file at the other end of my stdout looks okay!
[PASS] Success! You have satisfied all execution requirements.
I will write the flag in two parts to the file /home/hacker/the-flag! I'll do 
the first write directly to the file, and the second write, I'll do to stdout 
(if it's pointing at the file). If you redirect the output in append mode, the 
second write will append to (rather than overwrite) the first write, and you'll 
get the whole flag!
hacker@piping~appending-output:~$ /challenge/run >> /home/hacker/the-flag
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : /home/hacker/the-flag

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] Good luck!

[TEST] You should have redirected my stdout to a file called /home/hacker/the-flag. Checking...

[HINT] File descriptors are inherited from the parent, unless the FD_CLOEXEC is set by the parent on the file descriptor.
[HINT] For security reasons, some programs, such as python, do this by default in certain cases. Be careful if you are
[HINT] creating and trying to pass in FDs in python.

[PASS] The file at the other end of my stdout looks okay!
[PASS] Success! You have satisfied all execution requirements.
I will write the flag in two parts to the file /home/hacker/the-flag! I'll do 
the first write directly to the file, and the second write, I'll do to stdout 
(if it's pointing at the file). If you redirect the output in append mode, the 
second write will append to (rather than overwrite) the first write, and you'll 
get the whole flag!
hacker@piping~appending-output:~$ cat /home/hacker/the-flag
 | 
\|/ This is the first half:
 v 
pwn.college{0ODZWceNzpig46P-gpeCqdqa0rb.QX3ATO0wSN3kjNzEzW}
                              ^
     that is the second half /|\
                              |

If you only see the second half above, you redirected in *truncate* mode (>) 
rather than *append* mode (>>), and so the write of the second half to stdout 
overwrote the initial write of the first half directly to the file. Try append 
mode!

```
## Flag
pwn.college{0ODZWceNzpig46P-gpeCqdqa0rb.QX3ATO0wSN3kjNzEzW}

## What I learned
I learned how shell redirection works—specifically the difference between > (truncate) and >> (append). I saw that a
program can write data to a file itself and print more to stdout, so redirecting stdout with >> lets the printed output be appended to the file the program created, 
producing the complete result.

## Module 6.4 Redirecting Errors
## What I did
```
hacker@piping~redirecting-errors:~$ /challenge/run>myflag 2> instructions
hacker@piping~redirecting-errors:~$ cat myflag

[FLAG] Here is your flag:
[FLAG] pwn.college{8Tms-7EqfcWOljEjUt3n9yxUYMk.QX3YTN0wSN3kjNzEzW}


```
## Flag
pwn.college{8Tms-7EqfcWOljEjUt3n9yxUYMk.QX3YTN0wSN3kjNzEzW}

## What I learned
I learned how to redirect standard output and standard error separately: > (or 1>) sends stdout to a file while 2> sends stderr to another file.
By running the program with > myflag 2> instructions I captured the program’s normal output (the flag) in myflag and any diagnostic or instructional messages in instructions.

## Module 6.5 Redirecting Input
## What I did
```
hacker@piping~redirecting-input:~$ echo COLLEGE > PWN
hacker@piping~redirecting-input:~$ /challenge/run<PWN
Reading from standard input...
Correct! You have redirected the PWN file into my standard input, and I read 
the value 'COLLEGE' out of it!
Here is your flag:
pwn.college{YBFEJlgeO9IdPrInnYQdedZ-I4G.QXwcTN0wSN3kjNzEzW}

```
## Flag
pwn.college{YBFEJlgeO9IdPrInnYQdedZ-I4G.QXwcTN0wSN3kjNzEzW}

## What I learned
what did i learn?
ChatGPT said:

I learned how to redirect input into a program using <.
By writing COLLEGE into a file (echo COLLEGE > PWN) and then running /challenge/run < PWN, I made the program read its standard input from that file instead of the keyboard.

## Module 6.6 grepping stored results
## What I did
```
hacker@piping~grepping-stored-results:~$ /challenge/run > /tmp/data.txt
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : /tmp/data.txt
[INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /challenge/.data.txt file.

[TEST] You should have redirected my stdout to a file called /tmp/data.txt. Checking...

[HINT] File descriptors are inherited from the parent, unless the FD_CLOEXEC is set by the parent on the file descriptor.
[HINT] For security reasons, some programs, such as python, do this by default in certain cases. Be careful if you are
[HINT] creating and trying to pass in FDs in python.

[PASS] The file at the other end of my stdout looks okay!
[PASS] Success! You have satisfied all execution requirements.
hacker@piping~grepping-stored-results:~$ grep pwn.college /tmp/data.txt
pwn.college{oYJv3vLp9q7nHH9UmKqE2X-8wqg.QX4EDO0wSN3kjNzEzW}

```
## Flag
pwn.college{oYJv3vLp9q7nHH9UmKqE2X-8wqg.QX4EDO0wSN3kjNzEzW}
## What I learned
I learned how to search for specific text inside files using grep. By redirecting program output to a file and then using grep with a pattern like "pwn.college",
I can quickly find the flag without manually scanning through thousands of lines. This saves time and makes handling large outputs much easier.

## Module 6.7 grepping live output
## What I did
```
hacker@piping~grepping-live-output:~$ /challenge/run | grep pwn.college
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge checks for a specific process at the other end of stdout : grep
[INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /challenge/.data.txt file.

[TEST] You should have redirected my stdout to another process. Checking...
[TEST] Performing checks on that process!

[INFO] The process' executable is /nix/store/8b4vn1iyn6kqiisjvlmv67d1c0p3j6wj-gnugrep-3.11/bin/grep.
[INFO] This might be different than expected because of symbolic links (for example, from /usr/bin/python to /usr/bin/python3 to /usr/bin/python3.8).
[INFO] To pass the checks, the executable must be grep.

[PASS] You have passed the checks on the process on the other end of my stdout!
[PASS] Success! You have satisfied all execution requirements.
pwn.college{U7bqBLvin0pxEtrV7hX87BDYDIM.QX5EDO0wSN3kjNzEzW}
```
## Flag
pwn.college{U7bqBLvin0pxEtrV7hX87BDYDIM.QX5EDO0wSN3kjNzEzW}

## What I learned
I learned how piping works: by using |, I connected the output of /challenge/run directly into grep, making grep the process on the other end of stdout. The challenge checked that the receiving program was actually grep (not just a file), and since I piped correctly, it passed the tests and gave me the flag.

## Module 6.8 Grepping Errors
## What I did
```
hacker@piping~grepping-errors:~$ /challenge/run 2>&1 | grep pwn.college
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge checks for a specific process at the other end of stderr : grep
[INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /challenge/.data.txt file.

[TEST] You should have redirected my stderr to another process. Checking...
[TEST] Performing checks on that process!

[INFO] The process' executable is /nix/store/8b4vn1iyn6kqiisjvlmv67d1c0p3j6wj-gnugrep-3.11/bin/grep.
[INFO] This might be different than expected because of symbolic links (for example, from /usr/bin/python to /usr/bin/python3 to /usr/bin/python3.8).
[INFO] To pass the checks, the executable must be grep.

[PASS] You have passed the checks on the process on the other end of my stderr!
[PASS] Success! You have satisfied all execution requirements.
pwn.college{Yyuahum_P6gLsCgSj899spbokTj.QX1ATO0wSN3kjNzEzW}

```
## Flag
pwn.college{Yyuahum_P6gLsCgSj899spbokTj.QX1ATO0wSN3kjNzEzW}

## What I learned
I learned the difference between stdout and stderr: stdout (fd 1) is for normal program output, while stderr (fd 2) is for errors or diagnostic messages. The pipe (|) only works with stdout, so to grep through errors I had to redirect stderr into stdout using 2>&1 and then pipe the combined stream into grep to find the flag.

## Module 6.9 Filtering with grep -v
## What I did
```
hacker@piping~filtering-with-grep-v:~$ /challenge/run | grep -v DECOY
pwn.college{o5ONGj1cmVlXt4PA4BNQYD_kP6K.0FOxEzNxwSN3kjNzEzW}
```
## Flag
pwn.college{o5ONGj1cmVlXt4PA4BNQYD_kP6K.0FOxEzNxwSN3kjNzEzW}

## What I learned
I learned that giving another program’s name as an argument just passes it as text to the command, but it doesn’t actually run that program. To really connect two programs, I must use the pipe (|), which takes the output of one command and feeds it into another. That’s why /challenge/run grep -v DECOY didn’t work, but /challenge/run | grep -v DECOY did.

## Module 6.10 Duplicating piped data with tee
## What I did
```
hacker@piping~duplicating-piped-data-with-tee:~$ /challenge/pwn | tee output |/challenge/college
Processing...
WARNING: you are overwriting file output with tee's output...
The input to 'college' does not contain the correct secret code! This code 
should be provided by the 'pwn' command. HINT: use 'tee' to intercept the 
output of 'pwn' and figure out what the code needs to be.
hacker@piping~duplicating-piped-data-with-tee:~$ cat output
Usage: /challenge/pwn --secret [SECRET_ARG]

SECRET_ARG should be "g3BoEf5y"
hacker@piping~duplicating-piped-data-with-tee:~$ /challenge/pwn --secret g3BoEf5y | /challenge/college
Processing...
Correct! Passing secret value to /challenge/college...
Great job! Here is your flag:
pwn.college{g3BoEf5y4BBaxffWtBybFshotsL.QXxITO0wSN3kjNzEzW}
```
## Flag
pwn.college{g3BoEf5y4BBaxffWtBybFshotsL.QXxITO0wSN3kjNzEzW}

## What I learned
I learned to pipe /challenge/pwn into /challenge/college instead of passing program names as arguments. If output appears on stderr, I learned to merge it into stdout with 2>&1 before piping. I used tee to save a copy (e.g. /tmp/pwn_code) while still forwarding the stream, which let me inspect it, find a SECRET_ARG: value, and re-run /challenge/college with that value.


## Module 6.11 Process substitution for input
## What I did
```
hacker@piping~process-substitution-for-input:~$ diff <(/challenge/print_decoys) <(/challenge/print_decoys_and_flag)
19a20
> pwn.college{AAF_88s4LbN1D5ylU7QrfwJXVNC.0lNwMDOxwSN3kjNzEzW}
```
## Flag
pwn.college{AAF_88s4LbN1D5ylU7QrfwJXVNC.0lNwMDOxwSN3kjNzEzW}
## What I learned
I learned that Linux treats everything like a file, and with process substitution <(command) I can pass the output of a command to another command as if it were a file.

## Module 6.12 Writing to multiple programs
## What I did
```
hacker@piping~writing-to-multiple-programs:~$ /challenge/hack | tee >( /challenge/the ) | /challenge/planet
Congratulations, you have duplicated data into the input of two programs! Here 
is your flag:
pwn.college{4ra7jC0HV1TnI-vlK5dxQBoZFn9.QXwgDN1wSN3kjNzEzW}
```
## Flag
pwn.college{4ra7jC0HV1TnI-vlK5dxQBoZFn9.QXwgDN1wSN3kjNzEzW}

## What I learned
To feed the same output into multiple programs, I need to combine tee with process substitution >(program). That way, tee duplicates the stream and passes it into programs as if they were files, letting me run several commands on the same input simultaneously.

## Module 6.13 Split piping stderr and stdout
## What I did
```
hacker@piping~split-piping-stderr-and-stdout:~$ /challenge/hack 2> >( /challenge/the ) | /challenge/planet
Congratulations, you have learned a redirection technique that even experts 
struggle with! Here is your flag:
pwn.college{4FNNI9YNBBaO_Nn1koE8FDPs9HC.QXxQDM2wSN3kjNzEzW}

```
## Flag

pwn.college{4FNNI9YNBBaO_Nn1koE8FDPs9HC.QXxQDM2wSN3kjNzEzW}

## What I learned
I learned that if I want to redirect stderr or stdout into programs (not files), I need to use process substitution. Writing > file or 2> file just treats the path like a file, but >(command) runs the command and gives me a file-like handle to its stdin.

## Module 6.14 Named pipes
## What I did
```
hacker@piping~named-pipes:~$ mkfifo /tmp/flag_fifo
hacker@piping~named-pipes:~$ /challenge/run > /tmp/flag_fifo & cat /tmp/flag_fifo
You're successfully redirecting /challenge/run to a FIFO at /tmp/flag_fifo! 
Bash will now try to open the FIFO for writing, to pass it as the stdout of 
/challenge/run. Recall that operations on FIFOs will *block* until both the 
read side and the write side is open, so /challenge/run will not actually be 
launched until you start reading from the FIFO!
[1] 364
You've correctly redirected /challenge/run's stdout to a FIFO at 
/tmp/flag_fifo! Here is your flag:
pwn.college{4iLhyaEpdFrTZN-1qZ-a7oga2dS.01MzMDOxwSN3kjNzEzW}
[1]+  Done                    /challenge/run > /tmp/flag_fifo
```
## Flag
pwn.college{4iLhyaEpdFrTZN-1qZ-a7oga2dS.01MzMDOxwSN3kjNzEzW}
## What I learned
I learned that when I redirect output into a FIFO (named pipe), the writer will block until a reader opens the pipe. To avoid being stuck, I can either start a reader first (so the writer runs right away) or put the writer in the background with & and then start the reader.
