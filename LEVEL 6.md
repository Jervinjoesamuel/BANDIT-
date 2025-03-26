## Level 6 → Level 7

### Level Goal
The password for the next level is stored somewhere on the server and has all of the following properties:
- Owned by user `bandit7`
- Owned by group `bandit6`
- 33 bytes in size

### Commands Needed
- `ls` - List directory contents
- `cd` - Change directory
- `cat` - Display file contents
- `file` - Determine file type
- `du` - Estimate file space usage
- `find` - Search for files
- `grep` - Search for patterns within files

### Steps to Solve

1. **Connect to the Bandit server:**
   ```sh
   ssh bandit6@bandit.labs.overthewire.org -p 2220
   ```
   Password: (Use the password from Level 5)

2. **Use the `find` command to locate the file:**
   ```sh
   find / -type f -user bandit7 -group bandit6 -size 33c 2>/dev/null
   ```
   Explanation:
   - `/` - Search the entire system
   - `-type f` - Look for files
   - `-user bandit7` - Find files owned by user `bandit7`
   - `-group bandit6` - Find files owned by group `bandit6`
   - `-size 33c` - Find files that are exactly 33 bytes
   - `2>/dev/null` - Suppress error messages

3. **Display the password:**
   ```sh
   cat <file_path>
   ```
   Replace `<file_path>` with the actual path of the file found in the previous step.

  ![Image](https://github.com/user-attachments/assets/373931ab-4a51-49bf-ad2c-2d265ecb7111)

5. **Use the password to log in to the next level:**
   ```sh
   ssh bandit7@bandit.labs.overthewire.org -p 2220
   ```

---
Congratulations! You've completed Level 6 and moved to Level 7.

