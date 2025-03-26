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
