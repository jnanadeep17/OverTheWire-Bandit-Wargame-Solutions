# Level 8->Level 9
**Problem statement**:
<br>
The password for the next level is stored in the file data.txt and is the only line of text that occurs only once
<br>

## Solution
commands used: 
`ssh`, `ls`, `sort`, `uniq` <br>

### 1. Initiating the SSH connection:
First step is to connect to bandit8 user account using the password we found in the previous level, with the help of `ssh`.
<br>

**Provided credentials:** <br>
user : `bandit8` <br>
host : `bandit.labs.overthewire.org`<br>
password : `dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc`

`ssh bandit8@bandit.labs.overthewire.org -p 2220`
<br>

It prompts to enter the password, enter it.<br>

We are Successfully connected as `bandit8`!


### 2. Searching password for next level
The problem says the password is stored in the file data.txt and it's the line of text that occurs only once.
<br>

If we try to cat the file like earlier you will see long list of passwords, but we need a password that is unique. 
<br>

The solution is to use `sort` with `uniq -u`, sort arranges the data in ascending order and `uniq` filters out repeated adjacent lines from input, `-u` prints the line which is unique.

so the command will be 
```
sort data.txt | uniq -u
```
### Flag / password
You output will be
```
4CKMh1JI91bUIZZPXDqGanal4xvAg0JM
``` 
<br>

The password for bandit9 is : `4CKMh1JI91bUIZZPXDqGanal4xvAg0JM`