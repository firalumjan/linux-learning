# File Permissions

## Learning Objectives

By the end of this lesson, you will be able to:

- Understand Linux file permissions.
- Explain the difference between Owner, Group, and Others.
- Read permission strings such as `-rwxr-xr--`.
- Convert symbolic permissions to numeric permissions.
- Change file permissions using `chmod`.
- Change file ownership using `chown` and `chgrp`.

---

# What are File Permissions?

File permissions determine **who can read, write, or execute** a file or directory.

Every file and directory has permissions assigned to:

- Owner (User)
- Group
- Others

---

# Viewing Permissions

Use:

```bash
ls -l
```

Example:

```text
-rwxr-xr-- 1 najmul-arif najmul-arif 120 Jul 26 10:00 script.sh
```

---

# Understanding the Permission String

```text
-rwxr-xr--

│││ │││ │││
│││ │││ └┴┴── Others
│││ └┴┴────── Group
│└┴────────── Owner
└──────────── File Type
```

---

# File Types

| Symbol | Meaning | Example |
|---------|---------|---------|
| `-` | Regular file | notes.txt |
| `d` | Directory | Documents/ |
| `l` | Symbolic link | shortcut -> file.txt |

---

# Permission Types

| Symbol | Meaning |
|---------|---------|
| r | Read |
| w | Write |
| x | Execute |

---

# What Each Permission Means

## For Files

### Read (r)

View the file contents.

### Write (w)

Modify the file.

### Execute (x)

Run the file as a program or script.

---

## For Directories

### Read

List files inside the directory.

### Write

Create, rename, or delete files inside the directory.

### Execute

Enter the directory using:

```bash
cd directory_name
```

---

# Memory Trick

Remember:

```text
r = Read
w = Write
x = Execute
```

Think of a notebook:

- Read → Open and read it.
- Write → Edit it.
- Execute → Use it like an application.

---

# Numeric Permissions

Each permission has a numeric value.

| Permission | Value |
|------------|------:|
| Read | 4 |
| Write | 2 |
| Execute | 1 |

Add the values together.

| Number | Permission | Calculation |
|--------:|------------|-------------|
| 7 | rwx | 4 + 2 + 1 |
| 6 | rw- | 4 + 2 |
| 5 | r-x | 4 + 1 |
| 4 | r-- | 4 |
| 3 | -wx | 2 + 1 |
| 2 | -w- | 2 |
| 1 | --x | 1 |
| 0 | --- | 0 |

---

# Common Permission Examples

| Numeric | Owner | Group | Others | Common Use |
|---------:|-------|-------|--------|------------|
| 755 | rwx | r-x | r-x | Scripts and directories |
| 644 | rw- | r-- | r-- | Text files |
| 600 | rw- | --- | --- | Private files |
| 700 | rwx | --- | --- | Private executable scripts |
| 640 | rw- | r-- | --- | Shared within a group |
| 711 | rwx | --x | --x | Directories requiring traversal only |
| 777 | rwx | rwx | rwx | Full access (avoid in production) |

---

# Memory Trick for Numeric Permissions

```text
Read    = 4
Write   = 2
Execute = 1
```

Examples:

```text
rwx = 4+2+1 = 7

rw- = 4+2 = 6

r-x = 4+1 = 5

r-- = 4
```

If you remember **4**, **2**, and **1**, you can calculate any permission.

---

# chmod

Grant execute permission:

```bash
chmod +x script.sh
```

Remove execute permission:

```bash
chmod -x script.sh
```

Numeric examples:

```bash
chmod 755 script.sh

chmod 644 notes.txt

chmod 600 secret.txt
```

---

# chown

Change file owner.

```bash
sudo chown username file.txt
```

Owner and group together:

```bash
sudo chown username:developers file.txt
```

---

# chgrp

Change only the group.

```bash
sudo chgrp developers file.txt
```

---

# Check Current User

```bash
whoami

id

groups
```

---

# Practice Lab

Create files:

```bash
mkdir permissions

cd permissions

touch file644 file755 file600
```

Assign permissions:

```bash
chmod 644 file644

chmod 755 file755

chmod 600 file600
```

Verify:

```bash
ls -l
```

Expected output:

```text
-rw-r--r-- file644

-rwxr-xr-x file755

-rw------- file600
```

Try removing execute permission:

```bash
chmod -x file755

ls -l
```

Add it back:

```bash
chmod +x file755

ls -l
```

---

# Command Cheat Sheet

| Command | Purpose |
|----------|---------|
| ls -l | View permissions |
| chmod +x | Add execute permission |
| chmod -x | Remove execute permission |
| chmod 755 | Set rwxr-xr-x |
| chmod 644 | Set rw-r--r-- |
| chmod 600 | Set rw------- |
| chown | Change owner |
| chgrp | Change group |
| whoami | Current user |
| id | User ID and groups |
| groups | Show user groups |

---

# Interview Questions

### What are Linux file permissions?

They determine who can read, write, or execute a file or directory.

---

### What are the three permission categories?

- Owner
- Group
- Others

---

### What does `chmod 755 file.sh` do?

Sets permissions to:

```text
Owner : rwx

Group : r-x

Others: r-x
```

---

### What does `chmod +x script.sh` do?

Adds execute permission to the file.

---

### Which command changes a file's owner?

```bash
chown
```

---

### Which command changes a file's group?

```bash
chgrp
```

---

### What does the first character `d` mean in `drwxr-xr-x`?

It indicates that the item is a **directory**.

---

### What does permission `600` mean?

```text
Owner : Read + Write

Group : No permission

Others: No permission
```

---

### Why is `chmod 777` discouraged?

It gives everyone full read, write, and execute access, creating a serious security risk.

---

# Best Practices

- Use **644** for regular files.
- Use **755** for executable scripts and directories.
- Use **600** for sensitive files like SSH keys.
- Avoid **777** unless absolutely necessary.
- Follow the principle of least privilege by granting only the permissions that are required.

---

# Key Takeaways

- Linux permissions are divided into **Owner**, **Group**, and **Others**.
- Every permission consists of **Read**, **Write**, and **Execute**.
- `ls -l` displays permissions.
- `chmod` changes permissions.
- `chown` changes ownership.
- `chgrp` changes the group.
- Numeric permissions are calculated using **4 (Read) + 2 (Write) + 1 (Execute)**.
- Common permissions to remember are **755**, **644**, and **600**.

---

# Summary

After completing this lesson, you should be able to:

- Explain Linux file permissions.
- Interpret permission strings.
- Convert between symbolic and numeric permissions.
- Use `chmod`, `chown`, and `chgrp`.
- Apply common permission values correctly.
- Follow secure permission management practices.
