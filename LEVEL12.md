
# Bandit Level 12 → Level 13 Walkthrough

## Level Goal
The password for the next level is stored in the file `data.txt`, which is a hexdump of a file that has been repeatedly compressed. For this level, it may be useful to create a directory under `/tmp` in which you can work. Use `mkdir` with a hard-to-guess directory name or, better, use the command `mktemp -d`. Then copy the data file using `cp`, and rename it using `mv` (read the manpages!).

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
- `mkdir`
- `cp`
- `mv`
- `file`

## Helpful Reading Material
- [Hex dump on Wikipedia](https://en.wikipedia.org/wiki/Hex_dump)

## Steps to Solve

### Step 1: Connect to the Server
Use the following command to connect via SSH:
```bash
ssh bandit12@bandit.labs.overthewire.org -p 2220
```
Enter the password for `bandit12` when prompted.

### Step 2: Create a Temporary Working Directory
Create a unique temporary directory under `/tmp` and navigate into it:
```bash
tempdir=$(mktemp -d)
cd "$tempdir"
```

### Step 3: Copy and Convert the Hexdump Back to a File
Copy the `data.txt` file to your working directory:
```bash
cp ~/data.txt .
```
Convert the hexdump back to binary:
```bash
xxd -r data.txt > data.bin
```

### Step 4: Extract the Compressed Data
Use `file` to determine the file type:
```bash
file data.bin
```
Extract the file using the appropriate decompression tool. Repeat this process multiple times until you get a readable text file:
```bash
# If gzip compressed
gzip -d data.bin || mv data.bin data.gz && gunzip data.gz

# If bzip2 compressed
bzip2 -d data || mv data data.bz2 && bunzip2 data.bz2

# If tar archive
tar -xf data
```
If `file data` shows **bzip2 compressed data**, extract it with:
```bash
bzip2 -d data
```
Then, check the file type again:
```bash
file data.out
```
Repeat the extraction process until you reach a readable text file.

### Step 5: Retrieve the Password
Once fully decompressed, open the final text file and copy the password:
```bash
cat data
```
If the last extracted file is a gzip file:
```bash
mv data8.bin data8.gz
gunzip data8.gz
```
Check the file type again:
```bash
file data8
```
If it is ASCII text, view it:
```bash
cat data8
```

![Image](https://github.com/user-attachments/assets/ef5d2861-157f-4123-acea-1d8851b14ccb)

This should reveal the password for Bandit Level 13.

### Step 6: Log in to Bandit Level 13
Use the retrieved password to log in to Bandit Level 13 using SSH:
```bash
ssh bandit13@bandit.labs.overthewire.org -p 2220
```

Good luck with the next level!

