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


