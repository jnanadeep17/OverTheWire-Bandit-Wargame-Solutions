# Level 0->Level 1
**Problem statement**:
<br>
The goal of this level is for you to log into the game using SSH. The host to which you need to connect is bandit.labs.overthewire.org, on port 2220. The username is bandit0 and the password is bandit0. Once logged in, go to the Level 1 page to find out how to beat Level 1.



## Solution
commands used: 
`ssh`, `ls`, `cat`<br>

### 1. Initiating the SSH connection:
The first step is to connect to the remote server using `ssh`.
<br>

**Provided credentials:** <br>
user : `bandit0` <br>
host : `bandit.labs.overthewire.org`<br>
password : `bandit0`

`ssh bandit0@bandit.labs.overthewire.org -p 2220`
<br>

It prompts to enter the password, password is `bandit0`.<br>

We are Successfully connected to the server!


### 2. Searching password for next level
The next step is to find the password for the next level!.
So I use `ls` command to list out the files present in the present working directory

The `ls` command shows a single file named `readme`. I'll use the `cat` command to display its contents.


### Flag / password
The `cat readme` command outputs the password for the next level.<br>

The password for bandit1 is : `ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If`