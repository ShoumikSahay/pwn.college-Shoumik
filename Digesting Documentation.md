# Digesting Documentation
## Module 4.1 Learning from Documentation
## What I did
```
hacker@man~learning-from-documentation:~$ /challenge/challenge --giveflag
Correct argument! Here is your flag:
pwn.college{A8OJP8IKYb5_lBbgLdlp06io_iG.QX0ITO0wSN3kjNzEzW}
```
## Flag
pwn.college{A8OJP8IKYb5_lBbgLdlp06io_iG.QX0ITO0wSN3kjNzEzW}

## What I learned
In this challenge, I learned the importance of reading and understanding program documentation. Many command-line programs require specific arguments to function correctly, and knowing which argument to use can completely change the program’s behavior.

## Module 4.2 Learning Complex Usage
## What I did
```
hacker@man~learning-complex-usage:~$ /challenge/challenge --printfile /flag
Correct argument! Here is the /flag file:
pwn.college{g7Y2Csh2v8Mbbq4Xc1C5Pofjgm7.QX1ITO0wSN3kjNzEzW}

```
## Flag
pwn.college{g7Y2Csh2v8Mbbq4Xc1C5Pofjgm7.QX1ITO0wSN3kjNzEzW}

## What I learned
In this challenge, I learned about commands that take arguments to their arguments. The program /challenge/challenge required the --printfile argument, and that argument itself needed a file path to specify which file to print.

## Module 4.3 Reading Manuals
## What I did
```
hacker@man~reading-manuals:~$ man challenge
hacker@man~reading-manuals:~$ /challenge/challenge --eiwzxj 775
Correct usage! Your flag: pwn.college{QGeiG_-MwzQxSRF7Aj75tToZcx3.QX0EDO0wSN3kjNzEzW}

```
## Flag
pwn.college{QGeiG_-MwzQxSRF7Aj75tToZcx3.QX0EDO0wSN3kjNzEzW}

## What I learned
In this challenge, I learned how to identify and run executable files by their full path. By listing the contents of the /challenge directory, I determined that the file named challenge was the program to run.

## Module 4.4 Searching Manuals
## What I did
```
hacker@man~searching-manuals:~$ man challenge
hacker@man~searching-manuals:~$ /challenge/challenge --kva 
Initializing...
Correct usage! Your flag: pwn.college{MhnRhh7tVzgMQmmgyT56UorstyL.QX1EDO0wSN3kjNzEzW}
```
## Flag
pwn.college{MhnRhh7tVzgMQmmgyT56UorstyL.QX1EDO0wSN3kjNzEzW}

## What I learned
In this challenge, I learned how to locate and run an executable using its full path. By inspecting the /challenge directory, I identified the challenge file as the program to run. Reading the man page taught me how to supply the correct argument (--eiwzxj 775) so that the program would reveal the flag.

## Module 4.5 Searching for Manuals
## What I did
```
hacker@man~searching-for-manuals:~$ man man
hacker@man~searching-for-manuals:~$ man wxysrjgoaw
hacker@man~searching-for-manuals:~$ /challenge/challenge --wxysrj 477
Correct usage! Your flag: pwn.college{4wY7PxYHyWsQPVNr-jgB7oRa-NH.QX2EDO0wSN3kjNzEzW}

```
## Flag
pwn.college{4wY7PxYHyWsQPVNr-jgB7oRa-NH.QX2EDO0wSN3kjNzEzW}

## What I learned
In this challenge, I learned how to search for and use hidden manpages to understand how to run a command correctly. I also learned that commands can require specific options and numeric arguments, and reading the documentation carefully is essential to execute them properly and retrieve the flag.

## Module 4.6 Helpful programs
## What I did
```
hacker@man~helpful-programs:~$ /challenge/challenge --fortune
To be trusted is a greater compliment than to be loved.
hacker@man~helpful-programs:~$ /challenge/challenge --print-value
The secret value is: 253
hacker@man~helpful-programs:~$ 
hacker@man~helpful-programs:~$ /challenge/challenge -g 253
Correct usage! Your flag: pwn.college{oNWSD2-5RKhFK3_kVnFDUrAnyCE.QX3IDO0wSN3kjNzEzW}

```
## Flag
pwn.college{oNWSD2-5RKhFK3_kVnFDUrAnyCE.QX3IDO0wSN3kjNzEzW}

## What I learned
I learned that not all programs come with a man page, but many provide their own documentation when run with special options like --help or -h. This is a common way to quickly check how to use a program, what arguments it accepts, and what each argument does.

## Module 4.7 Help for Builtins
## What I did
```
hacker@man~help-for-builtins:~$ help challenge
challenge: challenge [--fortune] [--version] [--secret SECRET]
    This builtin command will read you the flag, given the right arguments!
    
    Options:
      --fortune		display a fortune
      --version		display the version
      --secret VALUE	prints the flag, if VALUE is correct

    You must be sure to provide the right value to --secret. That value
    is "gsHhkqak".
hacker@man~help-for-builtins:~$ challenge --secret gsHhkqak
Correct! Here is your flag!
pwn.college{gsHhkqakMyjtxUzwMfoHF7bY3g9.QX0ETO0wSN3kjNzEzW}

```
## Flag
pwn.college{gsHhkqakMyjtxUzwMfoHF7bY3g9.QX0ETO0wSN3kjNzEzW}

## What I learned
I learned that some commands are actually shell builtins, meaning they are handled directly by the shell instead of being separate programs. To get help with these builtins, you can use the help command instead of man or --help.
