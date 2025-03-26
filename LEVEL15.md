# Bandit Level 15 → Level 16 Walkthrough

## Level Goal

The password for the next level can be retrieved by submitting the password of the current level to port `30001` on `localhost` using SSL/TLS encryption.

## Commands You May Need

- `ssh`
- `nc` (netcat)
- `openssl s_client`
- `ncat`
- `socat`

---

## Step-by-Step Solution

### 1. Log in to Level 15

Use the provided credentials to log in to the Bandit server:

```sh
ssh bandit15@bandit.labs.overthewire.org -p 2220
```

Password for `bandit15` (from the previous level):

```
<PREVIOUS_PASSWORD>
```

### 2. Use OpenSSL to Send the Password

Since the communication requires SSL/TLS encryption, we use `openssl s_client`:

```sh
echo "<PREVIOUS_PASSWORD>" | openssl s_client -connect localhost:30001 -quiet
```

Alternatively, manually enter the password using OpenSSL:

```sh
openssl s_client -connect localhost:30001
```

When connected, type the password and press **Enter**.

### 3. Retrieve the Password for Level 16

After submitting the password, you will receive a response with the password for `bandit16`. It should look like this:

```
Correct! The password for bandit16 is <NEW_PASSWORD>
```

![Image](https://github.com/user-attachments/assets/9c6010b5-b1f3-4db7-b34e-d8ec02244d95)

Make sure to save this password for logging into Level 16.

### 4. Log in to Level 16

Now, use the new password to log in to the next level:

```sh
ssh bandit16@bandit.labs.overthewire.org -p 2220
```


