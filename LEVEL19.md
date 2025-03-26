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

