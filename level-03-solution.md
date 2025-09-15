# Level 3->Level 4
**Problem statement**:
<br>
The password for the next level is stored in a hidden file in the inhere directory.



## Solution
commands used: 
`ssh`, `cd` `ls`, `cat`<br>

### 1. Initiating the SSH connection:
First step is to connect to bandit3 user account using the password we found in the previous level, with the help of `ssh`.
<br>

**Provided credentials:** <br>
user : `bandit3` <br>
host : `bandit.labs.overthewire.org`<br>
password : `MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx`

`ssh bandit3@bandit.labs.overthewire.org -p 2220`
<br>

It prompts to enter the password, enter it.<br>

We are Successfully connected as `bandit3`!

### 2. Searching password for next level
The problem states that password for the next level is stored in a hidden file in the `inhere` directory.

The `ls` command shows a single file named `inhere` directory.
use `cd` command to move into the `inhere` folder.

If we try to list the files in `inhere` folder using `ls` command, it shows nothing.

The challenge here is to find the hidden file. To solve problem this we can use `ls -a` command which shows all the hidden files present in the directory.
`-a` stands for all including hidden files.

In our case this command lists out various things like `.` `..` `...Hiding-From-You`

We need to check this interesting file named `...Hiding-from-You`
 <br>



### Flag / password
The `cat ./...Hiding-from-You` command outputs the password for the next level.<br>

The password for bandit4 is : `2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ`