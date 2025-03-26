
# Bandit Level 10 → Level 11 Walkthrough

## Level Goal
The password for the next level is stored in the file `data.txt`, which contains base64 encoded data.

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
- [Base64 on Wikipedia](https://en.wikipedia.org/wiki/Base64)

## Steps to Solve

### Step 1: Connect to the Server
Use the following command to connect via SSH:
```bash
ssh bandit10@bandit.labs.overthewire.org -p 2220
```
Enter the password for `bandit10` when prompted.

### Step 2: Decode the Base64 Data
Run the following command to decode the base64-encoded content in `data.txt`:
```bash
base64 -d data.txt
```
#### Explanation:
- `base64 -d` → Decodes base64-encoded data in `data.txt`.

  

### Step 3: Retrieve the Password
The output of the command will display the decoded text. Identify and copy the password.

![Image](https://github.com/user-attachments/assets/de2c7826-50a0-4b4c-9805-bd44cd9d4317)

### Step 4: Log in to Bandit Level 11
Use the retrieved password to log in to Bandit Level 11 using SSH:
```bash
ssh bandit11@bandit.labs.overthewire.org -p 2220
```

Good luck with the next level!

