# Level 8->Level 9
**Problem statement**:
<br>
The password for the next level is stored in the file data.txt, which contains base64 encoded data
<br>

## Solution
commands used: 
`ssh`, `ls`, `strings`, `grep`<br>

### 1. Initiating the SSH connection:
First step is to connect to bandit10 user account using the password we found in the previous level, with the help of `ssh`.
<br>

**Provided credentials:** <br>
user : `bandit10` <br>
host : `bandit.labs.overthewire.org`<br>
password : `FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey`

`ssh bandit10@bandit.labs.overthewire.org -p 2220`
<br>

It prompts to enter the password, enter it.<br>

We are Successfully connected as `bandit10`!


### 2. Searching password for next level
The problem states that the password for the next level is in the file data.txt, which is base64 encoded
<br>

Our Target is to decode the base64 data
we can use `base64` to decode it
so the command will be 
```
base64 -d data.txt
```
`-d` is for decode
### Flag / password
The output will be

```
The password is dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr
``` 
<br>

The password for bandit11 is : `dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr`