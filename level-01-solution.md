# Level 1->Level 2
**Problem statement**:
<br>
The password for the next level is stored in a file called - located in the home directory



## Solution
commands used: 
`ssh`, `ls`, `cat`<br>

### 1. Initiating the SSH connection:
First step is to connect to bandit1 user account using the password we found in the previous level, with the help of `ssh`.
<br>

**Provided credentials:** <br>
user : `bandit1` <br>
host : `bandit.labs.overthewire.org`<br>
password : `ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If`

`ssh bandit1@bandit.labs.overthewire.org -p 2220`
<br>

It prompts to enter the password, enter it.<br>

We are Successfully connected as `bandit1`!


### 2. Searching password for next level

The `ls` command shows a single file named `-`. In this case the file name is tricky, a normal `cat -` doesn't work, the command will hang. <br> To solve this
 we have to specify the file's path. Since the file is in our current directory `.`, so we can refer it as `./-`


### Flag / password
The `cat ./-` command outputs the password for the next level.<br>

The password for bandit2 is : `263JGJPfgU6LtdEvgfWU1XP5yac29mFx`