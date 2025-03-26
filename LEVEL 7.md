
# Bandit Level 7 → Level 8 Walkthrough

## Level Goal
The password for the next level is stored in the file `data.txt` next to the word `millionth`.

## Commands You May Need
- `man`
- `grep`
- `sort`
- `uniq`
- `strings`
- `base64`
- `tr`
- `tar`
- `gzip`
- `bzip2`
- `xxd`

## Steps to Solve

### Step 1: Connect to the Server
Use the following command to connect via SSH:
```bash
ssh bandit7@bandit.labs.overthewire.org -p 2220
```
Enter the password for `bandit7` when prompted.

### Step 2: Locate the Password in `data.txt`
Run the following `grep` command to find the password:
```bash
grep 'millionth' data.txt
```
#### Explanation:
- `grep` → Searches for the word `millionth` in `data.txt`.

### Step 3: Retrieve the Password
The output of the `grep` command will display a line containing `millionth` and the corresponding password. Copy the password.

![Image](https://github.com/user-attachments/assets/d84fc122-43b3-435b-b840-4222f523ab3e)

### Step 4: Log in to Bandit Level 8
Use the retrieved password to log in to Bandit Level 8 using SSH:
```bash
ssh bandit8@bandit.labs.overthewire.org -p 2220
```

Good luck with the next level!

