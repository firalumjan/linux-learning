# Users and Groups

## What is a User?

A user is an account that can log in to a Linux system and use its resources.

Each user has:

- Username
- User ID (UID)
- Home directory
- Default shell
- Password

Example:

```
najmul-arif
```

---

## What is a Group?

A group is a collection of users.

Groups make it easier to manage permissions for multiple users.

Example:

```
developers
students
sudo
```

---

# Root User

The **root** user is the Linux administrator.

- Username: `root`
- UID: `0`
- Has unrestricted access to the entire system.

Check the root entry:

```bash
grep root /etc/passwd
```

---

# UID and GID

Every user has:

- **UID** (User ID)
- **GID** (Group ID)

View your UID and GID:

```bash
id
```

Example:

```text
uid=1000(najmul-arif)
gid=1000(najmul-arif)
```

---

# Important Files

## /etc/passwd

Stores user account information.

View:

```bash
cat /etc/passwd
```

Show first 10 lines:

```bash
head /etc/passwd
```

Find your account:

```bash
grep $(whoami) /etc/passwd
```

Example entry:

```text
najmul-arif:x:1000:1000:NAJMUL ARIF:/home/najmul-arif:/bin/bash
```

Fields:

```
username
password placeholder
UID
GID
comment
home directory
login shell
```

---

## /etc/group

Stores group information.

View:

```bash
cat /etc/group
```

Find the sudo group:

```bash
grep sudo /etc/group
```

---

## /etc/shadow

Stores encrypted passwords.

View (requires root):

```bash
sudo cat /etc/shadow
```

⚠️ Never edit this file manually.

---

# User Information Commands

Current user:

```bash
whoami
```

Current login:

```bash
logname
```

Display UID and GID:

```bash
id
```

Display groups:

```bash
groups
```

Who is logged in:

```bash
who
```

Show logged-in users and system activity:

```bash
w
```

---

# sudo

**sudo** stands for:

> **Super User Do**

Run a single command as root.

Example:

```bash
sudo apt update
```

---

# su

**su** means:

> **Substitute User** (or Switch User)

Become another user.

Example:

```bash
su -
```

Exit root:

```bash
exit
```

---

# User Management

## Create a User

```bash
sudo adduser username
```

Example:

```bash
sudo adduser testuser
```

---

## Change Password

```bash
sudo passwd username
```

Example:

```bash
sudo passwd testuser
```

---

## Delete User

Delete the user and home directory:

```bash
sudo deluser --remove-home username
```

Example:

```bash
sudo deluser --remove-home testuser
```

---

# Memory Tricks

## User Files

```
/etc/passwd
       │
       └── User information

/etc/group
       │
       └── Groups

/etc/shadow
       │
       └── Password hashes
```

Remember:

- **passwd** → User details
- **group** → Groups
- **shadow** → Hidden passwords

---

## whoami vs who

```
whoami
↓
ME

who
↓
Everyone logged in
```

---

## su vs sudo

```
su
↓
Become another user

sudo
↓
Run ONE command as another user
```

Example:

```bash
su -
```

Become the root user until you exit.

```bash
sudo apt install tree
```

Run only this command as root.

---

# Practice Commands

```bash
whoami
id
groups
who
w
logname

cat /etc/passwd | head
cat /etc/group | head

grep $(whoami) /etc/passwd
grep sudo /etc/group

sudo adduser testuser
id testuser
groups testuser
sudo deluser --remove-home testuser
```

---

# Summary

After completing this lesson, you should be able to:

- Explain users and groups.
- Understand UID and GID.
- Identify the root user.
- Understand the purpose of `/etc/passwd`, `/etc/group`, and `/etc/shadow`.
- Use `whoami`, `id`, `groups`, `who`, `w`, and `logname`.
- Create, modify, and delete users.
- Understand the difference between `su` and `sudo`.
