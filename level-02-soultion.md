# Level 2->Level 3
**Problem statement**:
<br>
The password for the next level is stored in a file called --spaces in this filename-- located in the home directory



## Solution
commands used: 
`ssh`, `ls`, `cat`<br>

### 1. Initiating the SSH connection:
First step is to connect to bandit2 user account using the password we found in the previous level, with the help of `ssh`.
<br>

**Provided credentials:** <br>
user : `bandit2` <br>
host : `bandit.labs.overthewire.org`<br>
password : `263JGJPfgU6LtdEvgfWU1XP5yac29mFx`

`ssh bandit2@bandit.labs.overthewire.org -p 2220`
<br>

It prompts to enter the password, enter it.<br>

We are Successfully connected as `bandit2`!


### 2. Searching password for next level
The problem states that the password is in file called `--spaces in this filename--` in home directory. we can use `ls` command to view the files.

The `ls` command shows a single file named `--spaces in this filename--`
 <br>

The challenge here is the spaces,we need to eliminate the spaces inorder to open the file, a normal `cat --spaces in this filename--` doesn't work.
 <br> 

There are two ways to solve this, the simple way is to wrap the file name in `" "` or `' '` quotes `cat ./"--spaces in the filename--"`<br>

The other way is to escape the spaces using backslash `\` like `cat ./--spaces\ in\ this\ filename--`


### Flag / password
The `cat ./"--spaces in this filename--"` command outputs the password for the next level.<br>

The password for bandit3 is : `MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx`