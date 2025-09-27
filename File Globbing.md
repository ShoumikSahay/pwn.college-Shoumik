# File Globbing
## Module 5.1 Matching with *
## What I did
```
hacker@globbing~matching-with-:~$ cd /ch*
hacker@globbing~matching-with-:/challenge$ /challenge/run
You ran me with the working directory of /challenge! Here is your flag:
pwn.college{MAHdxNMjIb5UzhCacE7ohHXgdJx.QXxIDO0wSN3kjNzEzW}

```
## Flag
pwn.college{MAHdxNMjIb5UzhCacE7ohHXgdJx.QXxIDO0wSN3kjNzEzW}

## What I learned
I learned how to use globbing in the shell to shorten paths and match directory or file names. 
Instead of typing out the full path /challenge, I used /ch*, and the shell expanded it to the correct directory.

## Module 5.2 Matching with ?
## What I did
```
hacker@globbing~matching-with-:~$ cd /?ha??enge
hacker@globbing~matching-with-:/challenge$ /challenge/run
You ran me with the working directory of /challenge! Here is your flag:
pwn.college{gJaVx-0WexTFt7nEM592U_UBURY.QXyIDO0wSN3kjNzEzW}

```
## Flag
pwn.college{gJaVx-0WexTFt7nEM592U_UBURY.QXyIDO0wSN3kjNzEzW}

## What I learned
hacker@globbing~matching-with-:~$ cd /?ha??enge
hacker@globbing~matching-with-:/challenge$ /challenge/run
You ran me with the working directory of /challenge! Here is your flag:
pwn.college{gJaVx-0WexTFt7nEM592U_UBURY.QXyIDO0wSN3kjNzEzW}

## Module 5.3 Matching with []
## What I did
```
hacker@globbing~matching-with-:~$ cd /challenge/files
hacker@globbing~matching-with-:/challenge/files$ /challenge/run file_[bash]
You got it! Here is your flag!
pwn.college{sR9dWwII9PzSKSo7ffjPDgjoEp8.QXzIDO0wSN3kjNzEzW}

```
## Flag
pwn.college{sR9dWwII9PzSKSo7ffjPDgjoEp8.QXzIDO0wSN3kjNzEzW}

## What I learned
I learned that using character-class globbing like file_[bash] lets me match filenames with a single character from the set. 
The shell expands the pattern, allowing me to pass the correct file to /challenge/run and get the flag.

## Module 5.4 Matching paths with []
## What I did
```
hacker@globbing~matching-paths-with-:~$ /challenge/run /challenge/files/file_[bash]
You got it! Here is your flag!
pwn.college{kxpzjmFopSCjgMLySkmztCgoM0-.QX0IDO0wSN3kjNzEzW}

```
## Flag
pwn.college{kxpzjmFopSCjgMLySkmztCgoM0-.QX0IDO0wSN3kjNzEzW}

## What I learned
I learned that I can use bracket globs to match multiple specific characters in filenames at once. By combining them in a single pattern, I can pass all the target files to /challenge/run and retrieve the flag.

## Module 5.5 Multiple globs
## What I did
```
Connected!                                                                        
hacker@globbing~multiple-globs:~$ cd /challenge/files
hacker@globbing~multiple-globs:/challenge/files$ /challenge/run *p*
You got it! Here is your flag!
pwn.college{U3JbI37rPV9Lc-sngIi1uPwilBJ.0lM3kjNxwSN3kjNzEzW}

```
## Flag
pwn.college{U3JbI37rPV9Lc-sngIi1uPwilBJ.0lM3kjNxwSN3kjNzEzW}

## What I learned
I learned how shell globbing expands patterns into matching filenames so a single argument can represent many files. Using *p* the shell matched all target files in /challenge/files and passed them to /challenge/run, letting me retrieve the flag without typing each filename.

## Module 5.6 Mixing globs
## What I did
```
hacker@globbing~mixing-globs:~$ cd /challenge/files
hacker@globbing~mixing-globs:/challenge/files$ /challenge/run [cep]*
You got it! Here is your flag!
pwn.college{0wGNEcXexCbA9QS-pKX0XxuEhx_.QX1IDO0wSN3kjNzEzW}

```
## Flag
pwn.college{0wGNEcXexCbA9QS-pKX0XxuEhx_.QX1IDO0wSN3kjNzEzW}

## What I learned
I learned how to combine multiple bracket globs into a single, short pattern to match multiple filenames at once. By using [cep]*, I could target files starting with specific letters without writing out each filename, keeping my command concise and efficient.

## Module 5.7 Exclusionary globbing
## What I did
```
hacker@globbing~exclusionary-globbing:~$ cd /challenge/files
hacker@globbing~exclusionary-globbing:/challenge/files$ /challenge/run [!pwn]*
You got it! Here is your flag!
pwn.college{spMD2NzYirVDLPGzFAXFmGoYtU1.QX2IDO0wSN3kjNzEzW}

```
## Flag
pwn.college{spMD2NzYirVDLPGzFAXFmGoYtU1.QX2IDO0wSN3kjNzEzW}

## What I learned
I learned how to use negated bracket globs to exclude certain filenames. By specifying [!pwn]*, I could match all files except those starting with p, w, or n, making my file selection more precise.

## Module 5.8 Tab Completion
## What I did
```
hacker@globbing~tab-completion:~$ cd /challenge
hacker@globbing~tab-completion:/challenge$ cat 
.bashrc         .init           DESCRIPTION.md  pwncollege​
hacker@globbing~tab-completion:/challenge$ cat pwncollege​ 
pwn.college{Utpbh31y2AB_CL9OqqMoATPguBO.0FN0EzNxwSN3kjNzEzW}

```
## Flag
pwn.college{Utpbh31y2AB_CL9OqqMoATPguBO.0FN0EzNxwSN3kjNzEzW}

## What I learned
I learned that blindly using * for file paths can be risky because it might match unintended files. A safer approach is tab completion, which helps me automatically complete filenames accurately, even if they have tricky or hidden characters.

## Module 5.9 Multiple options for Tab Completion
## What I did
```
hacker@globbing~multiple-options-for-tab-completion:~$ cd /challenge
hacker@globbing~multiple-options-for-tab-completion:/challenge/files$ cat pwn
No flag in this file!
hacker@globbing~multiple-options-for-tab-completion:/challenge/files$ cat pwn
pwn                    pwn-college            pwn-the-planet         pwncollege-family      pwncollege-flag        pwncollege-flamingo    pwncollege-flyswatter  pwncollege-hacking     
hacker@globbing~multiple-options-for-tab-completion:/challenge/files$ cat pwncollege-flag
pwn.college{A5noE93NC_VzaFFVkbSY9SampMq.0lN0EzNxwSN3kjNzEzW}

```
## Flag
pwn.college{A5noE93NC_VzaFFVkbSY9SampMq.0lN0EzNxwSN3kjNzEzW}

## What I learned
I learned that filenames can contain invisible or unusual characters, and that tab completion and commands like ls -b help reveal them. I also learned how to safely access files with tricky names to retrieve information, like a flag, without guessing the name blindly.

## Module 5.10 
## What I did
```
Connected!                                                                        
hacker@globbing~tab-completion-on-commands:~$ pwncollege-21592 
Correct! Here is your flag:
pwn.college{I931egQqy-dJcLJLMmLI1GQAYfe.0VN0EzNxwSN3kjNzEzW}


```
## Flag
pwn.college{I931egQqy-dJcLJLMmLI1GQAYfe.0VN0EzNxwSN3kjNzEzW}

## What I learned
I learned that tab completion works not just for filenames, but also for commands. It helps me discover and run hidden or tricky commands without typing the full name manually.
