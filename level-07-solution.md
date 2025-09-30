# Level 7->Level 8
**Problem statement**:
<br>
The password for the next level is stored in the file data.txt next to the word millionth
<br>

## Solution
commands used: 
`ssh`, `ls`, `cat`, `grep`<br>

### 1. Initiating the SSH connection:
First step is to connect to bandit7 user account using the password we found in the previous level, with the help of `ssh`.
<br>

**Provided credentials:** <br>
user : `bandit7` <br>
host : `bandit.labs.overthewire.org`<br>
password : `morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj`

`ssh bandit7@bandit.labs.overthewire.org -p 2220`
<br>

It prompts to enter the password, enter it.<br>

We are Successfully connected as `bandit7`!


### 2. Searching password for next level
The problem says the password is stored in the file data.txt next to the word millionth, if you try to `cat` the file, you will realize it's a very long file, and its impossible to find the word manually.
<br>
The solution is to use `grep` command, it helps us to find for exact word/patterns.

so the command will be 
```
cat data.txt | grep "millionth"
```
### Flag / password
The ouput will be something like
```
millionth       dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc
``` 
<br>

The password for bandit8 is : `dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc`