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
