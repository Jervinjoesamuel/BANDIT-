# Bandit Level 16 → Level 17 Walkthrough

## Level Goal

The credentials for the next level can be retrieved by submitting the password of the current level to a port on localhost in the range `31000` to `32000`. First, find out which of these ports have a server listening on them. Then, determine which of those use SSL/TLS. Only one server will provide the next credentials; the others will echo back whatever you send to them.

## Commands You May Need

- `ssh`
- `nmap`
- `nc` (netcat)
- `openssl s_client`
- `ncat`
- `socat`
- `netstat`
- `ss`

---

## Step-by-Step Solution

### 1. Log in to Level 16

Use the provided credentials to log in to the Bandit server:

```sh
ssh bandit16@bandit.labs.overthewire.org -p 2220
```

Password for `bandit16` (from the previous level):

```
<PREVIOUS_PASSWORD>
```

### 2. Scan for Open Ports in the Range 31000-32000

Use `nmap` to scan for open ports:

```sh
nmap -p 31000-32000 localhost
```

This will return a list of open ports.

### 3. Identify Which Ports Use SSL/TLS

For each open port, use `openssl s_client` to check if it supports SSL/TLS:

```sh
openssl s_client -connect localhost:<PORT>
```

If it successfully connects without errors, the port is using SSL/TLS.

### 4. Submit the Password to the Correct Port

Once the correct port is identified, send the current password to it:

```sh
echo "<PREVIOUS_PASSWORD>" | openssl s_client -connect localhost:<CORRECT_PORT> -quiet
```

Alternatively, manually enter the password after connecting:

```sh
openssl s_client -connect localhost:<CORRECT_PORT>
```
Then, type the password and press **Enter**.

### 5. Retrieve the Password for Level 17

If the correct port was used, you will receive the password for `bandit17`:

```
Correct! The password for bandit17 is <NEW_PASSWORD>
```

Save this password for the next level.

### 6. Log in to Level 17

Now, use the new password to log in to the next level:

```sh
ssh bandit17@bandit.labs.overthewire.org -p 2220
```
# Bandit Level 16 → Level 17 Walkthrough

## Level Goal

The credentials for the next level can be retrieved by submitting the password of the current level to a port on localhost in the range `31000` to `32000`. First, find out which of these ports have a server listening on them. Then, determine which of those use SSL/TLS. Only one server will provide the next credentials; the others will echo back whatever you send to them.

## Commands You May Need

- `ssh`
- `nmap`
- `nc` (netcat)
- `openssl s_client`
- `ncat`
- `socat`
- `netstat`
- `ss`

---

## Step-by-Step Solution

### 1. Log in to Level 16

Use the provided credentials to log in to the Bandit server:

```sh
ssh bandit16@bandit.labs.overthewire.org -p 2220
```

Password for `bandit16` (from the previous level):

```
kSkvUpMQ71BYyCM4GBPvCvT1BfWRy0Dx
```

### 2. Scan for Open Ports in the Range 31000-32000

Use `nmap` to scan for open ports:

```sh
nmap -p 31000-32000 localhost
```

This will return a list of open ports.

### 3. Identify Which Ports Use SSL/TLS

For each open port, use `openssl s_client` to check if it supports SSL/TLS:

```sh
openssl s_client -connect localhost:<PORT> -quiet
```

If it successfully connects without errors, the port is using SSL/TLS.

### 4. Submit the Password to the Correct Port

Once the correct port is identified (31790 in this case), send the current password to it:

```sh
echo "kSkvUpMQ71BYyCM4GBPvCvT1BfWRy0Dx" | openssl s_client -connect localhost:31790 -quiet
```

### 5. Retrieve the RSA Private Key for Level 17

If the correct port was used, you will receive an SSH private key. Copy the entire key, including the `BEGIN RSA PRIVATE KEY` and `END RSA PRIVATE KEY` lines, and save it to a file:

```sh
nano /tmp/bandit17_key
```

Paste the key into the file, then save and exit (CTRL+X, then Y, then Enter).

Change the file permissions to make it readable only by you:

```sh
chmod 600 /tmp/bandit17_key
```

### 6. Log in to Level 17 Using the RSA Key

Now, use the saved key to log in as `bandit17`:

```sh
ssh -i /tmp/bandit17_key bandit17@bandit.labs.overthewire.org -p 2220
```

---
