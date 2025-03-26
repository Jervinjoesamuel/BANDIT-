
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
