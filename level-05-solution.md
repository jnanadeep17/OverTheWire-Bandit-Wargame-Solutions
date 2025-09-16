# Level 5->Level 6
**Problem statement**:
<br>
The password for the next level is stored in a file somewhere under the inhere directory and has all of the following properties:

human-readable<br>
1033 bytes in size<br>
not executable

## Solution
commands used: 
`ssh`, `cd`, `ls`, `cat`, `find`<br>

### 1. Initiating the SSH connection:
First step is to connect to bandit5 user account using the password we found in the previous level, with the help of `ssh`.
<br>

**Provided credentials:** <br>
user : `bandit5` <br>
host : `bandit.labs.overthewire.org`<br>
password : `4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw`

`ssh bandit5@bandit.labs.overthewire.org -p 2220`
<br>

It prompts to enter the password, enter it.<br>

We are Successfully connected as `bandit5`!


### 2. Searching password for next level
The problem states that the password for next level is stored in a file somewhere under the `inhere` directory.
Conditions are it's a human-readable file, size 1033 bytes and not executable.

The `ls` command shows a single file named `inhere` directory.

use `cd` command to move into the `inhere` folder.

If we try to list the `inhere` folder using `ls` it shows many subdirectories

 ```
 maybehere00  maybehere02  maybehere04  maybehere06 maybehere08  maybehere10  maybehere12  maybehere14 maybehere16  maybehere18  maybehere01  maybehere03  maybehere05  maybehere07  maybehere09  maybehere11  maybehere13  maybehere15  maybehere17  maybehere19
 ```

We can search for the file manually, but it's time taking process.<br>

To solve this we can use the `find` command to search for a file with the properties given.

- File is 1033 bytes in size, so we use `-size 1033c` (c = bytes).

- File is not executable, so we use `! -executable`

So the full command is: `find . -size 1033c ! -executable`

the output will be something like
```
./maybehere07/.file2
```
The output shows the location of the file that matches the given properties.

### Flag / password
The `cat ./maybehere07/.file2` command outputs the password for the next level.<br>

The password for bandit6 is : `HWasnPhtq9AVKe0dmk45nxy20cvUa6EG`