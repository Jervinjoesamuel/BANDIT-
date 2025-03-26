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
