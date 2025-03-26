# Bandit Level 14 → Level 15 Walkthrough

## Level Goal
The password for the next level can be retrieved by submitting the password of the current level to port `30000` on `localhost`.

## Commands You May Need
- `ssh`
- `nc` (netcat)
- `telnet`

---

## Step-by-Step Solution

### 1. Log in to Level 14
Use the provided credentials to log in to the Bandit server:

```sh
ssh bandit14@bandit.labs.overthewire.org -p 2220
```

Password for `bandit14` (from the previous level):

```
BfMYroe26WYalil77FoDi9qh59eK5xNr
```

### 2. Use Netcat to Send the Password
The challenge requires sending the current password to `localhost` on port `30000`. Use the following command:

```sh
echo "BfMYroe26WYalil77FoDi9qh59eK5xNr" | nc localhost 30000
```

Alternatively, you can manually enter the password using Netcat:

```sh
nc localhost 30000
```
Then, type the password and press **Enter**.

### 3. Retrieve the Password for Level 15
After submitting the password, you will receive a response with the password for `bandit15`. It should look like this:

```
Correct! The password for bandit15 is <NEW_PASSWORD>
```

![Image](https://github.com/user-attachments/assets/d832e528-f562-420b-8700-c41bb0d0cd37)

Make sure to save this password for logging into Level 15.

### 4. Log in to Level 15
Now, use the new password to log in to the next level:

```sh
ssh bandit15@bandit.labs.overthewire.org -p 2220
```
