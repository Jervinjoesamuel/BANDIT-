
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
