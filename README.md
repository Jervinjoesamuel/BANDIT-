# Bandit Level 0 ➞ Level 1 Walkthrough

## **Introduction**
This guide explains how to complete Level 0 of the OverTheWire Bandit wargame and progress to Level 1 by retrieving the password stored in a file called `readme`.

## **Connection Details**
- **Username:** `bandit0`
- **Host:** `bandit.labs.overthewire.org`
- **Port:** `2220`
- **Password:** `bandit0` (default password for first login)

## **Steps to Solve Level 0**

### **1. Connect to Bandit Server**
Use the following SSH command to log in to Bandit Level 0:
```bash
ssh bandit0@bandit.labs.overthewire.org -p 2220
```
If prompted with a message about authenticity, type `yes` and press **Enter**.

When asked for a password, enter:
```
bandit0
```

### **2. Locate the Password File**
Once logged in, list the files in the home directory:
```bash
ls
```
You should see a file named `readme`.

### **3. Read the Password**
To display the contents of the `readme` file:
```bash
cat readme
```
![Image](https://github.com/user-attachments/assets/6c90f1ef-87db-4f0f-a76c-e3e9efaf3676)

This will reveal the password for **bandit1**.

### **4. Log in to Bandit Level 1**
Exit the current session:
```bash
exit
```
Then, log in to the next level using the retrieved password:
```bash
ssh bandit1@bandit.labs.overthewire.org -p 2220
```

# Bandit Level 1 ➞ Level 2 Walkthrough

## **Introduction**
This guide explains how to complete Level 1 of the OverTheWire Bandit wargame and progress to Level 2 by retrieving the password stored in a file named `-`.

## **Connection Details**
- **Username:** `bandit1`
- **Host:** `bandit.labs.overthewire.org`
- **Port:** `2220`
- **Password:** (obtained from Level 0's `readme` file)

## **Steps to Solve Level 1**

### **1. Connect to Bandit Server**
Use the following SSH command to log in to Bandit Level 1:
```bash
ssh bandit1@bandit.labs.overthewire.org -p 2220
```
When prompted, enter the password obtained from `readme` in Level 0.

### **2. Locate the Password File**
Once logged in, list the files in the home directory:
```bash
ls
```
You should see a file named `-`.

### **3. Read the Password from `-`**
Since `-` is a special character in Linux, using `cat -` will not work as expected. Instead, use:
```bash
cat ./-
```
or
```bash
cat -- -
```

![Image](https://github.com/user-attachments/assets/edf21e4a-b5ce-4a3c-bd99-68ec75cd29c1)

This will display the password for **bandit2**.

### **4. Log in to Bandit Level 2**
Exit the current session:
```bash
exit
```
Then, log in to the next level using the retrieved password:
```bash
ssh bandit2@bandit.labs.overthewire.org -p 2220
```
# Bandit Level 2 ➞ Level 3 Walkthrough

## **Introduction**
This guide explains how to complete Level 2 of the OverTheWire Bandit wargame and progress to Level 3 by retrieving the password stored in a file named `spaces in this filename`.

## **Connection Details**
- **Username:** `bandit2`
- **Host:** `bandit.labs.overthewire.org`
- **Port:** `2220`
- **Password:** (obtained from Level 1's `-` file)

## **Steps to Solve Level 2**

### **1. Connect to Bandit Server**
Use the following SSH command to log in to Bandit Level 2:
```bash
ssh bandit2@bandit.labs.overthewire.org -p 2220
```
When prompted, enter the password obtained from Level 1.

### **2. Locate the Password File**
Once logged in, list the files in the home directory:
```bash
ls
```
You should see a file named `spaces in this filename`.

### **3. Read the Password from `spaces in this filename`**
Since the filename contains spaces, you need to handle it correctly:

#### **Method 1: Using Quotes**
```bash
cat "spaces in this filename"
```

#### **Method 2: Using Escape Characters**
```bash
cat spaces\ in\ this\ filename
```

#### **Method 3: Using Tab Completion**
Type the first few letters and press `Tab` to autocomplete the filename:
```bash
cat spaces<Press TAB>
```

![Image](https://github.com/user-attachments/assets/a7e6d79f-abde-427e-84a8-52d8dd6ea853)

This will display the password for **bandit3**.

### **4. Log in to Bandit Level 3**
Exit the current session:
```bash
exit
```
Then, log in to the next level using the retrieved password:
```bash
ssh bandit3@bandit.labs.overthewire.org -p 2220
```
When prompted, enter the password obtained from `spaces in this filename`. 

# Bandit Level 3 ➞ Level 4 Walkthrough

## **Introduction**
This guide explains how to complete Level 3 of the OverTheWire Bandit wargame and progress to Level 4 by retrieving the password stored in a hidden file inside the `inhere` directory.

## **Connection Details**
- **Username:** `bandit3`
- **Host:** `bandit.labs.overthewire.org`
- **Port:** `2220`
- **Password:** (obtained from Level 2's `spaces in this filename` file)

## **Steps to Solve Level 3**

### **1. Connect to Bandit Server**
Use the following SSH command to log in to Bandit Level 3:
```bash
ssh bandit3@bandit.labs.overthewire.org -p 2220
```
When prompted, enter the password obtained from Level 2.

### **2. Locate the `inhere` Directory**
Once logged in, list the files in the home directory:
```bash
ls
```
You should see a directory named `inhere`.

### **3. Navigate to the `inhere` Directory**
Move into the `inhere` directory:
```bash
cd inhere
```

### **4. Find the Hidden File**
Since the file is hidden, use the `ls -a` command to list all files, including hidden ones:
```bash
ls -a
```
You should see a file prefixed with a dot (`.`), such as `.hidden`.

### **5. Read the Password from the Hidden File**
Use `cat` to display the content of the hidden file:
```bash
cat ...Hiding-From-You
```

![Image](https://github.com/user-attachments/assets/24bcc1e6-4c67-4411-9cd0-42e2db55fbc8)

This will display the password for **bandit4**.

### **6. Log in to Bandit Level 4**
Exit the current session:
```bash
exit
```
Then, log in to the next level using the retrieved password:
```bash
ssh bandit4@bandit.labs.overthewire.org -p 2220
```
When prompted, enter the password obtained from the hidden file.

# Bandit Level 4 ➞ Level 5 Walkthrough

## **Introduction**
This guide explains how to complete Level 4 of the OverTheWire Bandit wargame and progress to Level 5 by retrieving the password stored in the only human-readable file inside the `inhere` directory.

## **Connection Details**
- **Username:** `bandit4`
- **Host:** `bandit.labs.overthewire.org`
- **Port:** `2220`
- **Password:** (obtained from Level 3's hidden file)

## **Steps to Solve Level 4**

### **1. Connect to Bandit Server**
Use the following SSH command to log in to Bandit Level 4:
```bash
ssh bandit4@bandit.labs.overthewire.org -p 2220
```
When prompted, enter the password obtained from Level 3.

### **2. Locate the `inhere` Directory**
Once logged in, list the files in the home directory:
```bash
ls
```
You should see a directory named `inhere`.

### **3. Navigate to the `inhere` Directory**
Move into the `inhere` directory:
```bash
cd inhere
```

### **4. Identify the Human-Readable File**
Since multiple files may exist, we need to find the one that is human-readable. Use the `file` command to check file types:
```bash
file *
```
Look for the file labeled as `ASCII text` or `UTF-8 text`—this is the human-readable file.

### **5. Read the Password from the Human-Readable File**
Use `cat` to display the content of the correct file:
```bash
cat <filename>
```
Replace `<filename>` with the actual name of the human-readable file.

![Image](https://github.com/user-attachments/assets/0f373cd2-974a-4ec5-bb9f-b8428d2cf803)

This will display the password for **bandit5**.

### **6. Log in to Bandit Level 5**
Exit the current session:
```bash
exit
```
Then, log in to the next level using the retrieved password:
```bash
ssh bandit5@bandit.labs.overthewire.org -p 2220
```
When prompted, enter the password obtained from the human-readable file.

# Bandit Level 5 → Level 6 Walkthrough

## Level Goal
The password for the next level is stored in a file somewhere under the `inhere` directory and has all of the following properties:
- Human-readable
- 1033 bytes in size
- Not executable

## Commands Needed
You may need the following commands:
- `ls` - List directory contents
- `cd` - Change directory
- `cat` - Display file contents
- `file` - Determine file type
- `du` - Estimate file space usage
- `find` - Search for files

## Steps to Solve

1. **Connect to the Bandit server:**
   ```sh
   ssh bandit5@bandit.labs.overthewire.org -p 2220
   ```
   Password: (Use the password from Level 4)

2. **Navigate to the `inhere` directory:**
   ```sh
   cd inhere
   ```

3. **Find the file that matches the given criteria:**
   ```sh
   find . -type f -size 1033c ! -executable
   ```
   Explanation:
   - `find .` - Search in the current directory (`inhere` and its subdirectories)
   - `-type f` - Look for files (not directories)
   - `-size 1033c` - Find files that are exactly 1033 bytes
   - `! -executable` - Exclude executable files

4. **Display the password:**
   ```sh
   cat ./<filename>
   ```
   Replace `<filename>` with the actual file name found in the previous step.

   ![Image](https://github.com/user-attachments/assets/6de728c1-b34b-4e14-ad3f-cbb0ffe11da1)

6. **Use the password to log in to the next level:**
   ```sh
   ssh bandit6@bandit.labs.overthewire.org -p 2220
   ```

---
Congratulations! You've completed Level 5 and moved to Level 6.



## Level 5 → Level 6

### Level Goal
The password for the next level is stored in a file somewhere under the `inhere` directory and has all of the following properties:
- Human-readable
- 1033 bytes in size
- Not executable

### Commands Needed
You may need the following commands:
- `ls` - List directory contents
- `cd` - Change directory
- `cat` - Display file contents
- `file` - Determine file type
- `du` - Estimate file space usage
- `find` - Search for files

### Steps to Solve

1. **Connect to the Bandit server:**
   ```sh
   ssh bandit5@bandit.labs.overthewire.org -p 2220
   ```
   Password: (Use the password from Level 4)

2. **Navigate to the `inhere` directory:**
   ```sh
   cd inhere
   ```

3. **Find the file that matches the given criteria:**
   ```sh
   find . -type f -size 1033c ! -executable
   ```
   Explanation:
   - `find .` - Search in the current directory (`inhere` and its subdirectories)
   - `-type f` - Look for files (not directories)
   - `-size 1033c` - Find files that are exactly 1033 bytes
   - `! -executable` - Exclude executable files

4. **Display the password:**
   ```sh
   cat ./<filename>
   ```
   Replace `<filename>` with the actual file name found in the previous step.

5. **Use the password to log in to the next level:**
   ```sh
   ssh bandit6@bandit.labs.overthewire.org -p 2220
   ```

---

## Level 6 → Level 7

### Level Goal
The password for the next level is stored somewhere on the server and has all of the following properties:
- Owned by user `bandit7`
- Owned by group `bandit6`
- 33 bytes in size

### Commands Needed
- `ls` - List directory contents
- `cd` - Change directory
- `cat` - Display file contents
- `file` - Determine file type
- `du` - Estimate file space usage
- `find` - Search for files
- `grep` - Search for patterns within files

### Steps to Solve

1. **Connect to the Bandit server:**
   ```sh
   ssh bandit6@bandit.labs.overthewire.org -p 2220
   ```
   Password: (Use the password from Level 5)

2. **Use the `find` command to locate the file:**
   ```sh
   find / -type f -user bandit7 -group bandit6 -size 33c 2>/dev/null
   ```
   Explanation:
   - `/` - Search the entire system
   - `-type f` - Look for files
   - `-user bandit7` - Find files owned by user `bandit7`
   - `-group bandit6` - Find files owned by group `bandit6`
   - `-size 33c` - Find files that are exactly 33 bytes
   - `2>/dev/null` - Suppress error messages

3. **Display the password:**
   ```sh
   cat <file_path>
   ```
   Replace `<file_path>` with the actual path of the file found in the previous step.

  ![Image](https://github.com/user-attachments/assets/373931ab-4a51-49bf-ad2c-2d265ecb7111)

5. **Use the password to log in to the next level:**
   ```sh
   ssh bandit7@bandit.labs.overthewire.org -p 2220
   ```

---
Congratulations! You've completed Level 6 and moved to Level 7.

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

# Bandit Level 13 → Level 14 Walkthrough

## Level Goal
The password for the next level is stored in `/etc/bandit_pass/bandit14` and can only be read by the user `bandit14`. You are provided with an SSH private key that allows you to log in as `bandit14`.

## Steps to Solve

### 1. Log in to Bandit Level 13
Use the provided credentials to log in:
```sh
ssh bandit13@bandit.labs.overthewire.org -p 2220
```
Enter the password for `bandit13` when prompted.

### 2. Locate the SSH Private Key
Once logged in, list the files in the home directory:
```sh
ls -la
```
You should see a file named `sshkey.private`.

### 3. Use the Private Key to Log in as bandit14
Instead of using a password, authenticate using the private key:
```sh
ssh -i sshkey.private bandit14@localhost
```
If you receive a permission error, change the key's permissions:
```sh
chmod 600 sshkey.private
```
Then, try logging in again.

### 4. Retrieve the Password for Level 14
Once logged in as `bandit14`, read the password stored in `/etc/bandit_pass/bandit14`:
```sh
cat /etc/bandit_pass/bandit14
```
This will display the password needed for Level 14.

![Image](https://github.com/user-attachments/assets/fa3161d3-fa5b-4195-8f83-c0922e027284)

### 5. Log in to Bandit Level 14
Now, use the retrieved password to log into `bandit14` in a new session:
```sh
ssh bandit14@bandit.labs.overthewire.org -p 2220
```

## Commands Summary
- `ssh bandit13@bandit.labs.overthewire.org -p 2220` → Log into Level 13.
- `ls -la` → List files, including hidden ones.
- `ssh -i sshkey.private bandit14@localhost` → Use the private key to log in as `bandit14`.
- `chmod 600 sshkey.private` → Fix permission issues for the key.
- `cat /etc/bandit_pass/bandit14` → Retrieve the password.

Following these steps will successfully complete Level 13 and move on to Level 14.

# Bandit Level 14 → Level 15 Walkthrough

## Level Goal
The password for the next level can be retrieved by submitting the password of the current level to port `30000` on `localhost`.

## Commands You May Need
- `ssh`
- `nc` (netcat)
- `telnet`

---

## Step-by-Step Solution

### 1. Log in to Level 14
Use the provided credentials to log in to the Bandit server:

```sh
ssh bandit14@bandit.labs.overthewire.org -p 2220
```

Password for `bandit14` (from the previous level):

```
BfMYroe26WYalil77FoDi9qh59eK5xNr
```

### 2. Use Netcat to Send the Password
The challenge requires sending the current password to `localhost` on port `30000`. Use the following command:

```sh
echo "BfMYroe26WYalil77FoDi9qh59eK5xNr" | nc localhost 30000
```

Alternatively, you can manually enter the password using Netcat:

```sh
nc localhost 30000
```
Then, type the password and press **Enter**.

### 3. Retrieve the Password for Level 15
After submitting the password, you will receive a response with the password for `bandit15`. It should look like this:

```
Correct! The password for bandit15 is <NEW_PASSWORD>
```

![Image](https://github.com/user-attachments/assets/d832e528-f562-420b-8700-c41bb0d0cd37)

Make sure to save this password for logging into Level 15.

### 4. Log in to Level 15
Now, use the new password to log in to the next level:

```sh
ssh bandit15@bandit.labs.overthewire.org -p 2220
```

# Bandit Level 15 → Level 16 Walkthrough

## Level Goal

The password for the next level can be retrieved by submitting the password of the current level to port `30001` on `localhost` using SSL/TLS encryption.

## Commands You May Need

- `ssh`
- `nc` (netcat)
- `openssl s_client`
- `ncat`
- `socat`

---

## Step-by-Step Solution

### 1. Log in to Level 15

Use the provided credentials to log in to the Bandit server:

```sh
ssh bandit15@bandit.labs.overthewire.org -p 2220
```

Password for `bandit15` (from the previous level):

```
<PREVIOUS_PASSWORD>
```

### 2. Use OpenSSL to Send the Password

Since the communication requires SSL/TLS encryption, we use `openssl s_client`:

```sh
echo "<PREVIOUS_PASSWORD>" | openssl s_client -connect localhost:30001 -quiet
```

Alternatively, manually enter the password using OpenSSL:

```sh
openssl s_client -connect localhost:30001
```

When connected, type the password and press **Enter**.

### 3. Retrieve the Password for Level 16

After submitting the password, you will receive a response with the password for `bandit16`. It should look like this:

```
Correct! The password for bandit16 is <NEW_PASSWORD>
```

![Image](https://github.com/user-attachments/assets/9c6010b5-b1f3-4db7-b34e-d8ec02244d95)

Make sure to save this password for logging into Level 16.

### 4. Log in to Level 16

Now, use the new password to log in to the next level:

```sh
ssh bandit16@bandit.labs.overthewire.org -p 2220
```

# Bandit Level 16 → Level 17 Walkthrough

## Level Goal

The credentials for the next level can be retrieved by submitting the password of the current level to a port on localhost in the range `31000` to `32000`. First, find out which of these ports have a server listening on them. Then, determine which of those use SSL/TLS. Only one server will provide the next credentials; the others will echo back whatever you send to them.

## Commands You May Need

- `ssh`
- `nmap`
- `nc` (netcat)
- `openssl s_client`
- `ncat`
- `socat`
- `netstat`
- `ss`

---

## Step-by-Step Solution

### 1. Log in to Level 16

Use the provided credentials to log in to the Bandit server:

```sh
ssh bandit16@bandit.labs.overthewire.org -p 2220
```

Password for `bandit16` (from the previous level):

```
<PREVIOUS_PASSWORD>
```

### 2. Scan for Open Ports in the Range 31000-32000

Use `nmap` to scan for open ports:

```sh
nmap -p 31000-32000 localhost
```

This will return a list of open ports.

### 3. Identify Which Ports Use SSL/TLS

For each open port, use `openssl s_client` to check if it supports SSL/TLS:

```sh
openssl s_client -connect localhost:<PORT>
```

If it successfully connects without errors, the port is using SSL/TLS.

### 4. Submit the Password to the Correct Port

Once the correct port is identified, send the current password to it:

```sh
echo "<PREVIOUS_PASSWORD>" | openssl s_client -connect localhost:<CORRECT_PORT> -quiet
```

Alternatively, manually enter the password after connecting:

```sh
openssl s_client -connect localhost:<CORRECT_PORT>
```
Then, type the password and press **Enter**.

### 5. Retrieve the Password for Level 17

If the correct port was used, you will receive the password for `bandit17`:

```
Correct! The password for bandit17 is <NEW_PASSWORD>
```

Save this password for the next level.

### 6. Log in to Level 17

Now, use the new password to log in to the next level:

```sh
ssh bandit17@bandit.labs.overthewire.org -p 2220
```

# Bandit Level 16 → Level 17 Walkthrough

## Level Goal

The credentials for the next level can be retrieved by submitting the password of the current level to a port on localhost in the range `31000` to `32000`. First, find out which of these ports have a server listening on them. Then, determine which of those use SSL/TLS. Only one server will provide the next credentials; the others will echo back whatever you send to them.

## Commands You May Need

- `ssh`
- `nmap`
- `nc` (netcat)
- `openssl s_client`
- `ncat`
- `socat`
- `netstat`
- `ss`

---

## Step-by-Step Solution

### 1. Log in to Level 16

Use the provided credentials to log in to the Bandit server:

```sh
ssh bandit16@bandit.labs.overthewire.org -p 2220
```

Password for `bandit16` (from the previous level):

```
kSkvUpMQ71BYyCM4GBPvCvT1BfWRy0Dx
```

### 2. Scan for Open Ports in the Range 31000-32000

Use `nmap` to scan for open ports:

```sh
nmap -p 31000-32000 localhost
```

This will return a list of open ports.

### 3. Identify Which Ports Use SSL/TLS

For each open port, use `openssl s_client` to check if it supports SSL/TLS:

```sh
openssl s_client -connect localhost:<PORT> -quiet
```

If it successfully connects without errors, the port is using SSL/TLS.

### 4. Submit the Password to the Correct Port

Once the correct port is identified (31790 in this case), send the current password to it:

```sh
echo "kSkvUpMQ71BYyCM4GBPvCvT1BfWRy0Dx" | openssl s_client -connect localhost:31790 -quiet
```

### 5. Retrieve the RSA Private Key for Level 17

If the correct port was used, you will receive an SSH private key. Copy the entire key, including the `BEGIN RSA PRIVATE KEY` and `END RSA PRIVATE KEY` lines, and save it to a file:

```sh
nano /tmp/bandit17_key
```

Paste the key into the file, then save and exit (CTRL+X, then Y, then Enter).

Change the file permissions to make it readable only by you:

```sh
chmod 600 /tmp/bandit17_key
```

### 6. Log in to Level 17 Using the RSA Key

Now, use the saved key to log in as `bandit17`:

```sh
ssh -i /tmp/bandit17_key bandit17@bandit.labs.overthewire.org -p 2220
```

---

# Bandit Level 17 → Level 18 Walkthrough

## Level Goal
There are two files in the home directory: `passwords.old` and `passwords.new`. The password for the next level is in `passwords.new` and is the only line that has been changed between `passwords.old` and `passwords.new`.

## Commands You May Need
- `ls` – List files in the directory
- `cat` – Display contents of a file
- `diff` – Compare two files and show differences

## Solution
1. **Connect to Bandit Level 17**
   ```sh
   ssh bandit17@bandit.labs.overthewire.org -p 2220
   ```
   Password for Level 17 should be entered (retrieved from the previous level).

2. **List the files in the home directory**
   ```sh
   ls
   ```
   You should see `passwords.old` and `passwords.new`.

3. **Compare the two files using `diff`**
   ```sh
   diff passwords.old passwords.new
   ```
   Output:
   ```
   42c42
   < ktfgBvpMzWKR5ENj26IbLGSblgUG9CzB
   ---
   > x2gLTTjFwMOhQ8oWNbMN362QKxfRqGlO
   ```
   The `newpasswordline` is the password for Bandit Level 18.

4. **Retrieve and store the password**
   ```sh
   diff passwords.old passwords.new | grep '>' | cut -d ' ' -f2
   ```
   Output:
   ```
   x2gLTTjFwMOhQ8oWNbMN362QKxfRqGlO
   ```
![Image](https://github.com/user-attachments/assets/236c9935-2aeb-4774-aca9-9033854cf967)
  
   This extracts only the new password line.

4. **Log into Bandit Level 18**
   ```sh
   ssh bandit18@bandit.labs.overthewire.org -p 2220
   ```
   Use the retrieved password to access the next level.

## Notes
- If you see `Byebye!` when logging into Bandit 18, refer to the next level’s instructions for troubleshooting.
- The `diff` command highlights the changed lines, making it easy to find the new password.

---
**Password for Level 18:** `x2gLTTjFwMOhQ8oWNbMN362QKxfRqGlO`

---

# Bandit Level 18 → Level 19 Walkthrough

## Level Goal
The password for the next level is stored in a file named `readme` in the home directory. However, `.bashrc` has been modified to log you out immediately upon SSH login.

## Commands You May Need
- `ssh` – Connect to the server
- `cat` – Read file contents

## Solution
### 1. **Bypass `.bashrc` Execution**
Run the following command to read the password from `readme` without triggering the logout:
```sh
ssh bandit18@bandit.labs.overthewire.org -p 2220 "cat readme"
```
This directly retrieves the password for Bandit Level 19.

### 2. **Alternative: Start a Non-Interactive Shell**
If you want to explore the system manually, use:
```sh
ssh bandit18@bandit.labs.overthewire.org -p 2220 -t "bash --noprofile --norc"
```
This prevents `.bashrc` from executing and allows normal command input.

## Next Steps
Once you retrieve the password, use it to log into Bandit Level 19.

![Image](https://github.com/user-attachments/assets/67098efe-b93e-48e1-bc20-7244b8d84585)

---
**Password for Level 19:** `your_found_password_here` (replace with the actual password from `readme`)



---


# Bandit Level 19 → Level 20 Walkthrough

## Level Goal
To gain access to the next level, you should use the setuid binary in the home directory. Execute it without arguments to find out how to use it. The password for this level can be found in the usual place (`/etc/bandit_pass`), after you have used the setuid binary.

## Commands You May Need
- `ls` – List files in the directory
- `./<binary_name>` – Execute the setuid binary
- `cat` – Read file contents

## Solution
1. **Connect to Bandit Level 19**
   ```sh
   ssh bandit19@bandit.labs.overthewire.org -p 2220
   ```
   Enter the password retrieved from Level 18.

2. **Find the setuid binary**
   ```sh
   ls -l
   ```
   Look for a file with the setuid permission (`rwsr-xr-x`).

3. **Execute the binary**
   ```sh
   ./bandit20-do
   ```
   This should print usage instructions.

4. **Use the binary to read the password**
   ```sh
   ./bandit20-do cat /etc/bandit_pass/bandit20
   ```
![Image](https://github.com/user-attachments/assets/c950f3e7-c918-4529-8c5f-67acc0340689)
   
   This command runs `cat /etc/bandit_pass/bandit20` with elevated privileges, revealing the password for Level 20.
   

## Next Steps
Once you retrieve the password, use it to log into Bandit Level 20.

---
**Password for Level 20:** `your_found_password_here` (replace with the actual password from `/etc/bandit_pass/bandit20`)

---

# Bandit Level 20 → Level 21 Walkthrough

## Level Goal
There is a setuid binary in the home directory named `suconnect`. It connects to localhost on a specified port, reads a line of text from the connection, and compares it to the password from the previous level (Bandit 20). If correct, it returns the password for the next level (Bandit 21).

## Commands You May Need
- `ssh` – Connect to the server
- `nc` – Netcat for creating a listener
- `cat` – Read file contents
- `bash, screen, tmux` – Manage multiple sessions
- Unix Job Control (`bg, fg, jobs, &, CTRL-Z`)

## Solution
1. **Connect to Bandit Level 20**
   ```sh
   ssh bandit20@bandit.labs.overthewire.org -p 2220
   ```
   Enter the password retrieved from Level 19.

2. **Find the setuid binary**
   ```sh
   ls -l
   ```
   Look for a file named `suconnect` with the setuid permission (`rwsr-x---`).

3. **Start a Netcat listener in the background**
   ```sh
   nc -lvp 12345
   ```
   This opens a listening port (12345) to receive the password check request.

4. **Run `suconnect` with the same port**
   In another terminal (or using job control with `&`):
   ```sh
   ./suconnect 12345
   ```
   This will connect to the listener you started earlier.

   
![Image](https://github.com/user-attachments/assets/c1d35cc1-0443-46e4-99a3-a19f6035117c)



### Next Steps

Once you retrieve the password, use it to log into Bandit Level 21.



------------------------------------------------------THE END----------------------------------------------------------------------
