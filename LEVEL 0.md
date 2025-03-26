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
 
