# Level 6->Level 7
**Problem statement**:
<br>
The password for the next level is stored somewhere on the server and has all of the following properties:<br>

owned by user bandit7<br>
owned by group bandit6<br>
33 bytes in size

## Solution
commands used: 
`ssh`, `cd`, `ls`, `cat`, `file`<br>

### 1. Initiating the SSH connection:
First step is to connect to bandit6 user account using the password we found in the previous level, with the help of `ssh`.
<br>

**Provided credentials:** <br>
user : `bandit6` <br>
host : `bandit.labs.overthewire.org`<br>
password : `HWasnPhtq9AVKe0dmk45nxy20cvUa6EG`

`ssh bandit6@bandit.labs.overthewire.org -p 2220`
<br>

It prompts to enter the password, enter it.<br>

We are Successfully connected as `bandit6`!


### 2. Searching password for next level
The problem says the file is somewhere on the server, owned by `user bandit7`, `group bandit6`, and exactly `33 bytes` in size. 

To solve this we can use find command for this, as we know the file is anywhere on the server we need to use the command from the root `/`.

use `cd /` to change to the root direcotry 
- File is owned by user bandit7, so we use -user bandit7
- File is owned by group bandit6, so we use -group bandit6.
- File is 33 bytes in size, so we use -size 33c

Combining all these
the final command is 
```
find / -user bandit7 -group bandit6 -size 33c 2>/dev/null
```
<br>
here `2>/dev/null` ignores the permission denied error

the output will be something like

 ```
 /var/lib/dpkg/info/bandit7.password
 ```

### Flag / password

```
cat ./var/lib/dpkg/info/bandit7.password
``` 
The above command outputs the password for the next level.<br>

The password for bandit7 is : `morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj`