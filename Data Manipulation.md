# Module 8. Data Manipulation
## 8.1 Translating Charaters
## What I did
```
hacker@data~translating-characters:~$ /challenge/run
Your case-swapped flag:
PWN.COLLEGE{4k0d085xryl3joV4XWOVloGvCPH.01mXeZnXWsn3KJnZeZw}
echo PWN.COLLEGE{4k0d085xryl3joV4XWOVloGvCPH.01mXeZnXWsn3KJnZeZw} | tr 'a-zA-Z' 'A-Za-z'
pwn.college{4K0D085XRYL3JOv4xwovLOgVcph.01MxEzNxwSN3kjNzEzW}
```
## Flag
pwn.college{4K0D085XRYL3JOv4xwovLOgVcph.01MxEzNxwSN3kjNzEzW}
## What I learned
I learned how to use the tr command in Linux to translate or modify characters in a stream of data. By piping the output of one command into tr, I can replace, remove, or change the case of characters. For example, I used tr 'a-zA-Z' 'A-Za-z' to swap the case of all letters and restore the original text from a modified output.
## 8.2 Deleting Characters
## What I did
```
hacker@data~deleting-characters:~$ /challenge/run
Your character-stuffed flag:
p%w^%n.%c%o%l%l%e^g^%e{^c^Z^%v^%E^%G^%h^%0^r%8^%o%5A^v^%W%T^%V%m%p^%1^%X^%H%8^%Ggb%B^P^.^0^F^N^%x%Ez^%N%x^%w^%S%N^%3^%kj^N^%zE^%z%W^}^%
hacker@data~deleting-characters:~$ /challenge/run | tr -d ^%
Your character-stuffed flag:
pwn.college{cZvEGh0r8o5AvWTVmp1XH8GgbBP.0FNxEzNxwSN3kjNzEzW}
```
## Flag
pwn.college{cZvEGh0r8o5AvWTVmp1XH8GgbBP.0FNxEzNxwSN3kjNzEzW}
## What I learned
I learned how to pipe a program's output into tr to clean and transform text: I used tr -d '^%' to delete the unwanted ^ and % characters and restore the flag, and I also know I can swap letter case with tr 'a-zA-Z' 'A-Za-z'.

## 8.3 Deleting newlines
## What I did
```
hacker@data~deleting-newlines:~$ /challenge/run
Your line-split flag: 
p
w
n.
c
o
ll
e
ge{o
S6R
Cro9D
KDie
r
FA
_Tp
e
G5
U
hLj
b
.
0
V
N
x
Ez
N
x
w
S
N
3
kj
N
z
E
z
W
}

hacker@data~deleting-newlines:~$ /challenge/run | tr -d "\n"
Your line-split flag: pwn.college{oS6RCro9DKDierFA_TpeG5UhLjb.0VNxEzNxwSN3kjNzEzW}
```
## Flag
pwn.college{oS6RCro9DKDierFA_TpeG5UhLjb.0VNxEzNxwSN3kjNzEzW}
## What I learned
I learned how to remove newline characters from command output by piping into tr — for example, /challenge/run | tr -d "\n" combines a multi-line flag into a single continuous string. This taught me that tr can delete specific characters (like \n) from a stream, making it easy to reformat or clean up command output.

## 8.4 Extracting the first few lines with head
## What I did
```
hacker@data~extracting-the-first-lines-with-head:~$ /challenge/pwn | head -n 7 | /challenge/college
Congratulations, you piped the right codes!
pwn.college{Eb7J49o6hNAeSNdiPC_wOGKBJm8.0lNxEzNxwSN3kjNzEzW}
```
## Flag
pwn.college{Eb7J49o6hNAeSNdiPC_wOGKBJm8.0lNxEzNxwSN3kjNzEzW}
## What I learned
I learned how to chain multiple commands using pipes to control data flow between them. By using /challenge/pwn | head -n 7 | /challenge/college, I took only the first seven lines of output from one command and passed them as input to another. This showed me how powerful pipes are for combining commands to process data step by step.

## 8.5 Extracting specific sectons of text
## What I did
```
hacker@data~extracting-specific-sections-of-text:~$ /challenge/run | cut -d " " -f 2 | tr -d "\n"
pwn.college{MYDeFToNKy8YmKX0TzDtC4v3uIf.01NxEzNxwSN3kjNzEzW}
```
## Flag
pwn.college{MYDeFToNKy8YmKX0TzDtC4v3uIf.01NxEzNxwSN3kjNzEzW}

## What I learned
I learned to use cut to extract columns by specifying the delimiter with -d (in quotes when it’s a space) and the field with -f, then pipe the result into tr -d "\n" to remove newlines and join the characters into the full flag — for example: /challenge/run | cut -d ' ' -f <field> | tr -d "\n".

## 8.6 Sorting data
## What I did
```
hacker@data~sorting-data:~$ sort /challenge/flags.txt
ovm.bollege{3XCvBdePrs-lterl8kwDS0oDTHA.0FM0LDOwwSM2kjMzEzW}
ovm.colldge{4XBuBdeQsr-ltesl7jxDT0nEUGA.0FM0MDOwwSM3jjNyEzW}
ovn.bnlkegd{4WCvBdePsr-ltesl8kwDT0oDUHA.0FM0MCOxwSN2jjNzDzW}
ovn.bnlldge{4XCuAddQsr-ltesk8kxDT0oDTHA.0EL0MCOxwSN2jjNyEzW}
ovn.cnllefe{3XBvBdeQrr-ltesl7jxDT0oEUHA.0EM0LDOxvSN3jjNyEyW}
ovn.collefe{4WBuBdeQrr-lsesl8kxDT0nDTHA.0EM0MCOxvSM3kiNzEyV}
ovn.collefe{4XBvBceQss-ksdsl8kwCT0oDTHA.0FM0LDOxvSN2kiNzDyW}
owm.bnkldge{4XCuBceQss-ltesk8kwDS0oEUHA.0FM0MDNxwRN2kiMyDyV}
owm.bokkdge{3XCvBdeQrs-lsdrk7kwCT0nETGA.0FM0MCOxwSM3kjNzEzW}
owm.cnllefe{3XCuBddQsr-ltdsl7jxDT0oDTHA.0FL0MDNwvRN3kiNzDyW}
own.boklege{4XCvBceQss-lsdsk8kxCS0oEUHA.0FM0MCOxwSN3kjNzEyW}
own.cnkkege{4XCvBdeQss-ltesk7jxDT0oDUGA.0FL0MDOwvSN3kjNyEzW}
own.cnklege{3XCvBdeQrs-ltesl7jxDT0oEUGA.0EL0LDOxvRN2kjNyEyW}
own.cnklege{4XCvBceQrr-ltesl8jxDS0oDUGA.0FM0LDOxwSM2jjNzEzW}
own.cokldgd{4XCvBdeQss-lterk8kxDT0oEUHA.0FL0LDOwwSN3kjNzEzW}
own.cokldge{4WCuBcdQsr-ktdsl8kwDT0oDUHA.0FL0MDNxwSN3jjMzDyV}
own.colkdge{3WBvAcePss-lsesl7kxDT0oEUHA.0FL0LDOxvRN3kiNzDyW}
own.colkege{3XCvBdeQss-ltesl8kxDT0oETHA.0FM0MDOwwSN3kjNzEyW}
own.colldgd{3WCvBdeQss-ltdsl7jxDT0oDUHA.0EM0MCOxvRN3kiNzEyV}
own.colldge{3XCvAdeQsr-lterk8kxCT0oEUHA.0FM0LDOxvSN3jiNzDzW}
own.collefe{4XCvBceQss-lsesk8kwDT0oEUHA.0FM0MDOxwSN3kjNyEyW}
own.college{3XBvBdeQss-ktesk8kxDS0oDUHA.0EM0MDOxwSN3kjNzEyW}
own.college{4WCvAddPss-lsesl8jxCT0nEUGA.0FM0MDOxvSN2kiNzEzW}
own.college{4XCuBdeQsr-ltdsl8kwDS0oEUHA.0FL0MDOxwSN3kjNzEyW}
own.college{4XCvBddQss-ltesk8kxCT0oEUHA.0FM0LDOwwSN3kjNzEzW}
own.college{4XCvBdeQss-ktesl8kxDT0oEUHA.0FM0MDOwwSN3kjNzEzW}
pvm.bnklegd{3WCvAdeQss-ktdsl8jxDT0oDUHA.0FM0LDOxwSM3kjNzEzV}
pvm.bollege{3XCvAddQrs-ktesk7kxCT0oETHA.0EM0MCNxwRM3jjNzEyW}
pvm.cokkdge{4WCvAdeQss-ltesl7kxCT0oEUHA.0FL0MDOxwRN3kjMyDyW}
pvm.cokkdge{4XBvBdeQss-ktesk7kwCS0oEUHA.0EM0MCOwwRM3kiNzEzW}
pvm.coklege{4XCvBceQsr-ltesl8kxDT0oEUHA.0EM0MDOxwSM3kiNzEzW}
pvm.colldgd{3XCuAddQss-lterl7kwCS0oDUHA.0EM0MDNxwSN3kjNyDzV}
pvm.collegd{4XCvAdeQss-lterl8kxDT0oEUHA.0FM0MDOxwRM3kiMyEzV}
pvm.college{4XCvBdeQss-ktesl8kxDT0oEUGA.0FM0MDOxvRN3kjNzEzW}
pvn.bnllefd{4XBuAdeQss-ltdrl8kxCT0oETHA.0EM0MDOwvSN3kiMyDzW}
pvn.bollegd{4XBvBddQss-lterl8kwDT0nEUGA.0FM0MDOwwSN3kiNzEyW}
pvn.cnklege{4WCvBdeQrs-ktdrl8jwDT0oEUHA.0FL0MDNwvRM2jiMyDzV}
pvn.colkefe{4WCvBdeQss-ktesl8kxDT0oEUHA.0FM0MDOxwSN3kjNzEzW}
pvn.colkefe{4XCvBcdPss-lsesl8kxDS0oEUHA.0EM0LDOxwRN3kjNzEyW}
pvn.college{4XBuBcdPss-ltesl8jxDS0nDTHA.0FM0MCNxvRN3kiNyDyW}
pvn.college{4XCvAdeQrs-ltesl7kxDT0oEUHA.0EM0MDOxwSN3kjNzDyW}
pvn.college{4XCvBdeQrs-ktesl8kxDT0oEUHA.0FL0MDOxvSN3kjNzEzW}
pwm.bollefe{3XCvBceQss-ltesl8kxDS0oDTHA.0EM0LCNxwSN3jiMyDzW}
pwm.bollefe{4XCuBddPss-ltdsl8kwDT0oEUGA.0EL0MCNxwSN3kjNzDzV}
pwm.bollege{3WCvAdeQsr-ltesk7kxDT0nDTGA.0FL0LDOwwSM3kjMzEyW}
pwm.cnlkege{4WCvAddPrr-ltesl7kwDS0oEUHA.0FM0LDOwwSN2kjNzEzW}
pwm.cnlldgd{4XCuBdePss-ktesk8jxCT0oDTGA.0EM0LCOxvRN3kiMzEzV}
pwm.cokkegd{4XCvBdeQss-lserl7kxDS0oDUHA.0FL0MDOxwRN3kjMzEzW}
pwm.coklefd{4XCuBddQrs-ltesl8kxDT0oEUHA.0FM0MDOxwRN3kjNzEzW}
pwm.colkefe{3WCvBdePsr-ltdsk7jxDT0oETGA.0FM0MDNwwSM3kjMzEyW}
pwm.colkefe{4XBuBceQss-ltdsk8kxDS0oETHA.0FM0MCOxwSN3kjNzEzW}
pwm.colkege{4WCuBdeQss-ltdsk7kxCT0oEUHA.0EM0MDNxvRM3kjNzEyW}
pwm.colldge{4XBvBdeQss-ltdsl8kwCT0oDUHA.0EM0MCOxvSN3jjNzDzV}
pwm.collegd{4XCvBceQrr-ltesl8kxCS0oETHA.0FM0MCOwwSM3kjNzEzW}
pwm.college{4XCuBdeQss-ltesl8kxCT0oEUHA.0FM0MCOxwRN3kjNzEzW}
pwm.college{4XCvBdeQrr-ktdrl8kwDT0nEUHA.0EL0LDNxvSN3kjNzEzV}
pwn.boklege{4XBvBdePrs-kterk8kxDT0oDTHA.0FM0LDOxvSN3jjNzDzW}
pwn.boklege{4XCvBcePrr-ksesl8kwCT0oEUHA.0FM0MDOxvSM3jjMzDzW}
pwn.bolkege{4WCvBddQss-ltesl7kxDT0oEUHA.0FM0LDOwwSN3kjNzDyW}
pwn.bollege{4WCvBdePss-ltesl8kwDT0oEUGA.0FM0MCNxwSN3kjNzEzW}
pwn.bollege{4XCuBddQss-ltesl8kxDT0oEUGA.0FM0MDOxwSN3kjMzEyW}
pwn.cnkldfe{4WCvBddQrr-ltesl8kxCS0oEUHA.0FM0LDOxvSM3kiNzEzW}
pwn.cnklefe{4XCuBddQrr-ltesl8kxDT0oEUHA.0EM0MDOxwSM3kjNzEzW}
pwn.cnklege{4XCuAdeQss-ktesl7kxDT0oEUHA.0FM0MCOwvSN3kjNyEyW}
pwn.cnklege{4XCvBdePss-ltesl8kxDT0nEUHA.0FM0MDOxwSN3kjNzEzW}
pwn.cnlldge{3XBvAddQrr-ltesk7kwCT0oEUHA.0FM0LCOxwRN3jiNzEzW}
pwn.cnllegd{4WBvAdeQss-ktesk8kxDT0oEUHA.0FL0LCNwwSN3kiNzDzW}
pwn.cnllege{4XBvBdeQss-lsdsk7kwDT0oEUGA.0FM0MDOxwSN3jjNyEzW}
pwn.cnllege{4XCvBddQsr-lsesk8kxDT0nEUHA.0EM0MDOxwSN3kjNzEyW}
pwn.cnllege{4XCvBdeQss-ktesk8kxDT0oEUHA.0FM0MDOxwSN3kjNzEzW}
pwn.cnllege{4XCvBdeQss-ltesl8kxDT0oEUHA.0FM0MDOxwSN3kjNzEzW}
pwn.cokkefd{4XCvAdeQss-lsesl8kxDS0oEUHA.0FL0LDOxwSN2kiNzEzW}
pwn.colkdge{3XCvBddQss-ksesl8kxCS0oEUHA.0FM0LCOxvRM3jjMyEyW}
pwn.colkdge{4WCvBceQss-ltesk8kxCS0oDUHA.0FM0MDNwvSN3kjNzEzW}
pwn.colkefe{4WCuBddQss-kterl8kxDT0oETGA.0EL0MCOxwSM3jiNzEzW}
pwn.colkefe{4XCuBdeQss-lserl8kwDT0nDUGA.0FM0MDOxwSN3kjNzEzV}
pwn.colkege{4XCvBdeQss-ltdsl8kxDT0oEUHA.0FM0MDOxwSN3kiNyEzW}
pwn.colldge{4WCuBddQss-ksdrl8kxCT0nEUGA.0EL0MDOwwSM3kjMzEyW}
pwn.colldge{4XBvBdeQsr-lsdsl7kxDS0nDUGA.0FM0LDNxwRN3kjMzDyW}
pwn.colldge{4XCuBcdQss-lsesl8kxDT0oDUGA.0EM0LDOwwRM3kjNzEzW}
pwn.collefe{4XCvBdeQss-ktesl8kxCT0oEUHA.0FM0MDOxvSN3kjNzEzW}
pwn.collegd{3XBvBdeQss-ltesl8kxDT0oETHA.0FL0LDOwwSM3kjNzEzW}
pwn.college{3XCuBdePrs-ltdsk8jxDT0oEUHA.0FM0MDOxwRN2kjMzEzW}
pwn.college{3XCvAdeQss-ltesk8kxCS0nDTGA.0FM0MDNwwSN3kjNyDzW}
pwn.college{3XCvBceQss-lsesl8kwDT0nEUGA.0FL0MDOxwSN3kiNyEyW}
pwn.college{3XCvBdeQsr-ltesl8kxDT0oEUHA.0FM0MDOxwSN3jjNzEzW}
pwn.college{4WCuBdeQsr-ltesl7kxDT0nEUHA.0FM0MDOwwSN3kiMzEzW}
pwn.college{4WCvBdePsr-ltesl8kxDT0oEUHA.0EM0MDOxwSN3kjNzEzV}
pwn.college{4XBvAdePss-ltesl8jxCT0oEUHA.0FM0MDOxwSN3kjNzEzV}
pwn.college{4XCuBceQss-ltesl8kxDS0nETHA.0FM0MDOxwSN3kjNzEyW}
pwn.college{4XCvAdeQss-ltdrl8kxDT0oEUHA.0FL0MCNxvSN2kjMzEzW}
pwn.college{4XCvAdeQss-ltesl8kxCT0oEUHA.0FL0MDOxwRN3kjNzEzW}
pwn.college{4XCvBddQss-ltesl8kxDT0oEUHA.0FM0MDOxwSN3kjNzEzW}
pwn.college{4XCvBdePss-ltdsl8kxDT0oETHA.0FM0MDOxwSN3kjNzDyW}
pwn.college{4XCvBdeQrs-lterk8kxDT0oETGA.0FL0MDOxwSN2kjNzEzW}
pwn.college{4XCvBdeQss-lsesl8kxDT0oDUHA.0FM0MDOxwSN3kjNzEzW}
pwn.college{4XCvBdeQss-lterl8kxDT0oEUHA.0FM0LDOwwSN2kjNzEzW}
pwn.college{4XCvBdeQss-ltesl8kxDS0nEUHA.0FM0MDOxwSN3jjNzEzW}
pwn.college{4XCvBdeQss-ltesl8kxDT0oEUHA.0FM0LDOxwSM3kjNzEzW}
pwn.college{4XCvBdeQss-ltesl8kxDT0oEUHA.0FM0MDOxwSM3kjNzEzW}
pwn.college{4XCvBdeQss-ltesl8kxDT0oEUHA.0FM0MDOxwSN3kjNzEzW}

```
## Flag
pwn.college{4XCvBdeQss-ltesl8kxDT0oEUHA.0FM0MDOxwSN3kjNzEzW}


## What I learned
I learned how to use sort to organize data alphabetically and find specific items. By sorting /challenge/flags.txt, I can bring the real flag to the end of the list and then extract it easily.








