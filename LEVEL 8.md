
# Bandit Level 8 → Level 9 Walkthrough

## Level Goal
The password for the next level is stored in the file `data.txt` and is the only line of text that occurs only once.

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

## Helpful Reading Material
- Piping and Redirection

## Steps to Solve

### Step 1: Connect to the Server
Use the following command to connect via SSH:
```bash
ssh bandit8@bandit.labs.overthewire.org -p 2220
```
Enter the password for `bandit8` when prompted.

### Step 2: Find the Unique Line in `data.txt`
Run the following command to locate the password:
```bash
sort data.txt | uniq -u
```
![Image](https://github.com/user-attachments/assets/1a9cdee0-7027-4150-988e-4916182124e3)

#### Explanation:
- `sort` → Sorts the lines in `data.txt`.
- `uniq -u` → Displays only the unique line (occurs only once).

### Step 3: Retrieve the Password
The output of the command will display the unique line, which is the password. Copy the password.

### Step 4: Log in to Bandit Level 9
Use the retrieved password to log in to Bandit Level 9 using SSH:
```bash
ssh bandit9@bandit.labs.overthewire.org -p 2220
```

Good luck with the next level!

