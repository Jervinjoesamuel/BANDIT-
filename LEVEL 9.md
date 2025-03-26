# Bandit Level 9 → Level 10 Walkthrough

## Level Goal
The password for the next level is stored in the file `data.txt` in one of the few human-readable strings, preceded by several ‘=` characters.

## Commands You May Need
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
ssh bandit9@bandit.labs.overthewire.org -p 2220
```
Enter the password for `bandit9` when prompted.

### Step 2: Extract Human-Readable Strings
Run the following command to find readable strings in `data.txt`:
```bash
strings data.txt | grep '='
```
![Image](https://github.com/user-attachments/assets/f58ec8c4-a3b5-4d86-8834-82cdf15b478d)

#### Explanation:
- `strings` → Extracts human-readable text from `data.txt`.
- `grep '='` → Filters lines containing `=` characters, which precede the password.

### Step 3: Retrieve the Password
The output of the command will display lines with `=` characters. Identify the password in the output and copy it.

### Step 4: Log in to Bandit Level 10
Use the retrieved password to log in to Bandit Level 10 using SSH:
```bash
ssh bandit10@bandit.labs.overthewire.org -p 2220
```

Good luck with the next level!
