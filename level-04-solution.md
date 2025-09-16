# Level 4->Level 5
**Problem statement**:
<br>
The password for the next level is stored in the only human-readable file in the inhere directory. Tip: if your terminal is messed up, try the “reset” command.



## Solution
commands used: 
`ssh`, `cd`, `ls`, `cat`, `file`<br>

### 1. Initiating the SSH connection:
First step is to connect to bandit4 user account using the password we found in the previous level, with the help of `ssh`.
<br>

**Provided credentials:** <br>
user : `bandit4` <br>
host : `bandit.labs.overthewire.org`<br>
password : `2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ`

`ssh bandit4@bandit.labs.overthewire.org -p 2220`
<br>

It prompts to enter the password, enter it.<br>

We are Successfully connected as `bandit4`!


### 2. Searching password for next level
The problem states that the password for next level is stored in a human-readable file within `inhere` directory.

The `ls` command shows a single file named `inhere` directory.

use `cd` command to move into the `inhere` folder.

If we try to list the files in `inhere` folder using `ls` it shows many files

 ```
 -file00  -file01  -file02  -file03  -file04  -file05  -file06  -file07  -file08  -file09
 ```

We can search for password in each and every file, but it's time taking process, and we know password is only in human-readable file.
To solve this we can use the `file` command.

In our case there are many files, we should also note that the file name is starting with `-` so we it's better to use `./`

 `file ./*` (`*` here means all files)

the output will be something like
```
./-file00: data
./-file01: data
./-file02: data
./-file03: data
./-file04: data
./-file05: data
./-file06: data
./-file07: ASCII text
./-file08: data
./-file09: data
```
The output clearly shows that `./-file07` is ASCII text, which is the human-readable file.

### Flag / password
The `cat ./-file07` command outputs the password for the next level.<br>

The password for bandit5 is : `4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw`