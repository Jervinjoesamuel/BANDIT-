
# Bandit Level 11 → Level 12 Walkthrough

## Level Goal
The password for the next level is stored in the file `data.txt`, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions.

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
- [Rot13 on Wikipedia](https://en.wikipedia.org/wiki/ROT13)

## Steps to Solve

### Step 1: Connect to the Server
Use the following command to connect via SSH:
```bash
ssh bandit11@bandit.labs.overthewire.org -p 2220
```
Enter the password for `bandit11` when prompted.

### Step 2: Decode the ROT13 Text
Run the following command to decode the ROT13-encoded content in `data.txt`:
```bash
cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
```
#### Explanation:
- `cat data.txt` → Reads the contents of `data.txt`.
- `tr 'A-Za-z' 'N-ZA-Mn-za-m'` → Applies ROT13 decryption by shifting letters back 13 places.



### Step 3: Retrieve the Password
The output of the command will display the decoded text. Identify and copy the password.

![Image](https://github.com/user-attachments/assets/431a0541-c8c3-469c-9183-ed13e2f9fbc1)

### Step 4: Log in to Bandit Level 12
Use the retrieved password to log in to Bandit Level 12 using SSH:
```bash
ssh bandit12@bandit.labs.overthewire.org -p 2220
```

Good luck with the next level!

