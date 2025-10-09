# Module 12. 
## 12.1 Chaining with Semicolons
## What I did
```
hacker@chaining~chaining-with-semicolons:~$ /challenge/pwn;/challenge/college
Yes! You chained /challenge/pwn and /challenge/college! Here is your flag:
pwn.college{0GDO-H5NWzpSIQF0cK_H927kFmM.QX1UDO0wSN3kjNzEzW}
```
## Flag
pwn.college{0GDO-H5NWzpSIQF0cK_H927kFmM.QX1UDO0wSN3kjNzEzW}
## What I learned
I learned how to chain multiple commands on a single line in the shell using a semicolon (;). This allows me to execute one command after another without waiting for the first to finish and for the prompt to reappear. For example, I can run /challenge/pwn; /challenge/college to make both commands execute in sequence automatically.

## 12.2 Building on Success
## What I did
```
hacker@chaining~building-on-success:~$ /challenge/first-success 
hacker@chaining~building-on-success:~$ /challenge/second 
Error: /challenge/first-success must be successfully chained with 
/challenge/second using &&
hacker@chaining~building-on-success:~$ /challenge/first-success && /challenge/second
Nice chaining! Flag: pwn.college{sypNxHj1Lw4tr3D_GGC-Up0yVYk.0lM0MDOxwSN3kjNzEzW}

```
## Flag
pwn.college{sypNxHj1Lw4tr3D_GGC-Up0yVYk.0lM0MDOxwSN3kjNzEzW}
## What I learned
I learned how to chain commands with && so the second command only runs if the first succeeds. By testing /challenge/first-success and /challenge/second individually I saw neither gave the flag, but running /challenge/first-success && /challenge/second made the shell run the second command only after the first returned success — which produced the flag.

## 12.3 Handling Failiure
## What I did
```
hacker@chaining~handling-failure:~$ /challenge/first-failure || /challenge/second
Nice chaining! Flag: pwn.college{kE_gKzT6vTbFBbhc1TduTYv--XS.01M0MDOxwSN3kjNzEzW}

```
## Flag
pwn.college{kE_gKzT6vTbFBbhc1TduTYv--XS.01M0MDOxwSN3kjNzEzW}
## What I learned
I learned how to use the || operator to run a second command only if the first one fails. It’s useful for creating fallback options or handling errors in shell commands. In this challenge, when /challenge/first-failure didn’t succeed, the || operator made /challenge/second run automatically, allowing me to still get the desired result.

## 12.4 Your First Shell Script
## What I did
```
hacker@chaining~your-first-shell-script:~$ 
echo -e "/challenge/pwn\n/challenge/college" > x.sh


bash x.sh
Great job, you've written your first shell script! Here is the flag:
pwn.college{kw20yjG_jbRDw0l-ZvNXyWY1NiM.QXxcDO0wSN3kjNzEzW}
```
## Flag
pwn.college{kw20yjG_jbRDw0l-ZvNXyWY1NiM.QXxcDO0wSN3kjNzEzW}
## What I learned
I learned that putting two quoted paths next to each other (e.g. '/challenge/pwn''/challenge/college') makes the shell treat them as one token, which tried to run /challenge/pwn/challenge/college and caused an error. I also learned the correct way is to place each command on its own line (or separate with ;) inside a script

## 12.5 Redirecting Script Output
## What I did
```
hacker@chaining~redirecting-script-output:~$ echo "/challenge/pwn; /challenge/college" > x.sh && chmod +x x.sh && ./x.sh | /challenge/solve
./x.sh: /nix/store/0nxvi9r5ymdlr2p24rjj9qzyms72zld1-bash-interactive-5.2p37/share/bashdb/bashdb-main.inc: No such file or directory
./x.sh: warning: cannot start debugger; debugging mode disabled
Correct! Here is your flag:
pwn.college{4A64MMwOJFFyvl4NolDcr6dVekB.QX4ETO0wSN3kjNzEzW}
```
## Flag
pwn.college{4A64MMwOJFFyvl4NolDcr6dVekB.QX4ETO0wSN3kjNzEzW}
## What I learned
I learned how to use the pipe (|) operator to send the output of one command (or script) directly into another command as input. In this challenge, I created a script that ran /challenge/pwn and /challenge/college, then piped its output into /challenge/solve. I also understood that piping connects the output of the left command to the input of the right command, so I must pipe the script’s output—not the script creation command itself.

## 12.6 Executable Shell Scripts
## What I did
```
hacker@chaining~executable-shell-scripts:~$ echo "/challenge/solve" > x.sh
hacker@chaining~executable-shell-scripts:~$ chmod +x x.sh
hacker@chaining~executable-shell-scripts:~$ ./x.sh
Congratulations on your shell script execution! Your flag:
pwn.college{8GZ4yYOwoWI7dyvMMIUY64BMNmI.QX0cjM1wSN3kjNzEzW}
```
## Flag
pwn.college{8GZ4yYOwoWI7dyvMMIUY64BMNmI.QX0cjM1wSN3kjNzEzW}
## What I learned
I learned to create an executable shell script by writing the command to a file, using chmod +x to make it runnable, and executing ./x.sh to run /challenge/solve directly — which produced the flag.

## 12.7 Understanding Shebangs
## What I did
```
hacker@chaining~understanding-shebangs:~$ echo -e '#!/bin/bash\necho "hack the planet"'>/home/hacker/solve.sh
hacker@chaining~understanding-shebangs:~$ chmod +x /home/hacker/solve.sh
hacker@chaining~understanding-shebangs:~$ /challenge/run
Testing your script...
Perfect! Your flag:
Flag: pwn.college{wCMKkhqB3T37kNauYBEzrWGCTdN.0VOzMDOxwSN3kjNzEzW}

```
## Flag
Flag: pwn.college{wCMKkhqB3T37kNauYBEzrWGCTdN.0VOzMDOxwSN3kjNzEzW}

## What I learned
I learned to write a script /home/hacker/solve.sh with a shebang that prints "hack the planet", make it executable (chmod +x), and verify it using /challenge/run.

## 12.8 Scripting with Arguments
## What I did
```
hacker@chaining~scripting-with-arguments:~$ echo -e '#!/bin/bash\necho "$2" "$1"' > /home/hacker/solve.sh
hacker@chaining~scripting-with-arguments:~$ bash /home/hacker/solve.sh shoumik sahay
sahay shoumik
hacker@chaining~scripting-with-arguments:~$ /challenge/run
Correct! Your script properly reversed the arguments.
Here's your flag:
pwn.college{Qd6Le3xYAnklBr5-LZm1dfnyaZO.0VNzMDOxwSN3kjNzEzW}
```
## Flag
pwn.college{Qd6Le3xYAnklBr5-LZm1dfnyaZO.0VNzMDOxwSN3kjNzEzW}
## What I learned
I learned to create an executable shell script `/home/hacker/solve.sh` that accepts two arguments and prints them in reverse order (second then first), then run `/challenge/run` to verify it.

## 12.9 Scripting with conditionals
## What I did
```
hacker@chaining~scripting-with-conditionals:~$ echo -e '#!/bin/bash\nif [ "$1" = "pwn" ]; then\n  echo "college"\nfi' > /home/hacker/solve.sh
hacker@chaining~scripting-with-conditionals:~$  chmod +x /home/hacker/solve.sh
hacker@chaining~scripting-with-conditionals:~$ /challenge/run
Correct! Your script properly handles all the conditions.
Here's your flag:
pwn.college{0TB05v0sEmL4GNBmkuIcxpi_8MH.0lNzMDOxwSN3kjNzEzW}

```
## Flag
pwn.college{0TB05v0sEmL4GNBmkuIcxpi_8MH.0lNzMDOxwSN3kjNzEzW}
## What I learned
I learned to create an executable script /home/hacker/solve.sh that takes one argument and prints college only when that argument is pwn.

## 12.10 Scripting with Default Cases
## What I did
```
hacker@chaining~scripting-with-default-cases:~$  echo -e '#!/bin/bash\nif [ "$1" = "pwn" ]; then\n  echo "college"\nelse\n  echo "nope"\nfi' > /home/hacker/solve.sh
hacker@chaining~scripting-with-default-cases:~$ $ chmod +x /home/hacker/solve.sh
/challenge/run
bash: $: command not found
Correct! Your script properly handles the if/else conditions.
Here's your flag:
pwn.college{AEG5Sf0O6XKqeM31hkeR7fk3xfy.01NzMDOxwSN3kjNzEzW}

```
## Flag
pwn.college{AEG5Sf0O6XKqeM31hkeR7fk3xfy.01NzMDOxwSN3kjNzEzW}
## What I learned
I learned to write /home/hacker/solve.sh with a shebang that takes one argument, uses if [ "$1" = "pwn" ]; then echo college; else :; fi so the else is present but produces no output, make it executable with chmod +x, and verify with /challenge/run.

## 12.11
## What I did
```

```
## Flag

## What I learned

## 12.12 
## What I did
```

```
## Flag

## What I learned




