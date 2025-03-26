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

