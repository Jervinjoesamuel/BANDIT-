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
