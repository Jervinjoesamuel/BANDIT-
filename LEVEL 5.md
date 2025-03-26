# Bandit Level 5 → Level 6 Walkthrough

## Level Goal
The password for the next level is stored in a file somewhere under the `inhere` directory and has all of the following properties:
- Human-readable
- 1033 bytes in size
- Not executable

## Commands Needed
You may need the following commands:
- `ls` - List directory contents
- `cd` - Change directory
- `cat` - Display file contents
- `file` - Determine file type
- `du` - Estimate file space usage
- `find` - Search for files

## Steps to Solve

1. **Connect to the Bandit server:**
   ```sh
   ssh bandit5@bandit.labs.overthewire.org -p 2220
   ```
   Password: (Use the password from Level 4)

2. **Navigate to the `inhere` directory:**
   ```sh
   cd inhere
   ```

3. **Find the file that matches the given criteria:**
   ```sh
   find . -type f -size 1033c ! -executable
   ```
   Explanation:
   - `find .` - Search in the current directory (`inhere` and its subdirectories)
   - `-type f` - Look for files (not directories)
   - `-size 1033c` - Find files that are exactly 1033 bytes
   - `! -executable` - Exclude executable files

4. **Display the password:**
   ```sh
   cat ./<filename>
   ```
   Replace `<filename>` with the actual file name found in the previous step.

   ![Image](https://github.com/user-attachments/assets/6de728c1-b34b-4e14-ad3f-cbb0ffe11da1)

6. **Use the password to log in to the next level:**
   ```sh
   ssh bandit6@bandit.labs.overthewire.org -p 2220
   ```

---
Congratulations! You've completed Level 5 and moved to Level 6.



## Level 5 → Level 6

### Level Goal
The password for the next level is stored in a file somewhere under the `inhere` directory and has all of the following properties:
- Human-readable
- 1033 bytes in size
- Not executable

### Commands Needed
You may need the following commands:
- `ls` - List directory contents
- `cd` - Change directory
- `cat` - Display file contents
- `file` - Determine file type
- `du` - Estimate file space usage
- `find` - Search for files

### Steps to Solve

1. **Connect to the Bandit server:**
   ```sh
   ssh bandit5@bandit.labs.overthewire.org -p 2220
   ```
   Password: (Use the password from Level 4)

2. **Navigate to the `inhere` directory:**
   ```sh
   cd inhere
   ```

3. **Find the file that matches the given criteria:**
   ```sh
   find . -type f -size 1033c ! -executable
   ```
   Explanation:
   - `find .` - Search in the current directory (`inhere` and its subdirectories)
   - `-type f` - Look for files (not directories)
   - `-size 1033c` - Find files that are exactly 1033 bytes
   - `! -executable` - Exclude executable files

4. **Display the password:**
   ```sh
   cat ./<filename>
   ```
   Replace `<filename>` with the actual file name found in the previous step.

5. **Use the password to log in to the next level:**
   ```sh
   ssh bandit6@bandit.labs.overthewire.org -p 2220
   ```

---

