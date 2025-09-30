# Level 8->Level 9
**Problem statement**:
<br>
The password for the next level is stored in the file data.txt in one of the few human-readable strings, preceded by several ‘=’ characters.
<br>

## Solution
commands used: 
`ssh`, `ls`, `strings`, `grep`<br>

### 1. Initiating the SSH connection:
First step is to connect to bandit9 user account using the password we found in the previous level, with the help of `ssh`.
<br>

**Provided credentials:** <br>
user : `bandit9` <br>
host : `bandit.labs.overthewire.org`<br>
password : `4CKMh1JI91bUIZZPXDqGanal4xvAg0JM`

`ssh bandit9@bandit.labs.overthewire.org -p 2220`
<br>

It prompts to enter the password, enter it.<br>

We are Successfully connected as `bandit9`!


### 2. Searching password for next level
The problem says the password is in the file data.txt in one of the few human-readable string, preceded by several '=' characters

If we use `cat` command we can see mostly gibberish,
<br>

The solution is to use `strings` it shows human-redable sequence of characters, after this we can use `grep` to find the strings with `=`.

so the command will be 
```
strings data.txt | grep '='
```
The output contains a list of character sequence which includes `=`

But we are interested in something that is preceded by several `=` characters
```
========== the
S=s*$u
[=u~]/
hW\=
=}y2|
=RiaT
1j=\
========== password
f=+n
Q========== is%
="K@
n7X=
F<'=
!=v5~6
>u`9J========== FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey
Fb=G
```
### Flag / password

```
>u`9J========== FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey
``` 
<br>

The password for bandit10 is : `FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey`