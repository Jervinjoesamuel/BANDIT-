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
