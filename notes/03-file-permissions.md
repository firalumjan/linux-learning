# File Permissions

## What are File Permissions?

File permissions determine who can read, write, or execute a file or directory.

Every file and directory has permissions assigned to:

- Owner (User)
- Group
- Others

---

## Viewing Permissions

Use:

```bash
ls -l
```

Example output:

```text
-rwxr-xr-- 1 najmul-arif najmul-arif 120 Jul 26 10:00 script.sh
```

---

### Permission Layout

```text
-rwxr-xr--

│││ │││ │││
│││ │││ └┴┴── Others
│││ └┴┴────── Group
│└┴────────── Owner
└──────────── File Type
```

---

## File Types

| Symbol | Meaning | Example |
|---------|---------|---------|
| - | Regular file | notes.txt |
| d | Directory | Documents/ |
| l | Symbolic link | shortcut -> file.txt |

---

## Permission Types

| Symbol | Meaning |
|---------|---------|
| r | Read |
| w | Write |
| x | Execute |

---

## What Each Permission Means

### For Files

Read (r)
- View file contents.

Write (w)
- Modify the file.

Execute (x)
- Run the file as a program or script.

### For Directories

Read
- List files inside the directory.

Write
- Create, rename, or delete files in the directory.

Execute
- Enter the directory using `cd`.

---

## Numeric Permissions

| Number | Permission |
|---------|------------|
| 7 | rwx |
| 6 | rw- |
| 5 | r-x |
| 4 | r-- |
| 3 | -wx |
| 2 | -w- |
| 1 | --x |
| 0 | --- |

### Common Permission Examples

| Numeric | Owner | Group | Others | Meaning |
|---------|-------|-------|--------|---------|
| 644 | rw- | r-- | r-- | Regular text files |
| 755 | rwx | r-x | r-x | Scripts and directories |
| 600 | rw- | --- | --- | Private files |
| 777 | rwx | rwx | rwx | Full access (not recommended) |

---

## Memory Trick for Numeric Permissions

Each permission has a numeric value:

| Permission | Value |
|------------|------:|
| Read (r) | 4 |
| Write (w) | 2 |
| Execute (x) | 1 |

Add the values together to get the permission number.

Examples:

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

### Easy Memory Table

| Number | Meaning | Common Use |
|--------:|---------|------------|
| 755 | Owner: rwx, Group: r-x, Others: r-x | Executable scripts and directories |
| 644 | Owner: rw-, Group: r--, Others: r-- | Regular text files |
| 600 | Owner: rw-, Group: ---, Others: --- | Private files (SSH keys, passwords) |
| 777 | Owner: rwx, Group: rwx, Others: rwx | Full access (avoid in production) |

### Quick Tip

Think of the numbers as simple addition:

```text
r = 4
w = 2
x = 1

rwx = 4 + 2 + 1 = 7
rw- = 4 + 2 = 6
r-x = 4 + 1 = 5
r-- = 4 = 4
```

If you can remember **4 = Read**, **2 = Write**, and **1 = Execute**, you can calculate any Linux permission without memorizing every combination.

> **⚠️ Warning**
>
> Avoid using `chmod 777` unless absolutely necessary.
> It gives read, write, and execute permissions to everyone, which can create serious security risks.

## chmod

Add execute permission:

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

## chown

Change owner:

```bash
sudo chown username file.txt
```

Change owner and group:

```bash
sudo chown username:group file.txt
```

---

## chgrp

Change group:

```bash
sudo chgrp developers file.txt
```

---

## Check Current User

```bash
whoami
id
groups
```

---

## Summary

After completing this lesson, you should be able to:

- Explain Owner, Group, and Others.
- Understand Read, Write, and Execute permissions.
- Read permission strings such as `-rwxr-xr--`.
- Convert between symbolic and numeric permissions.
- Use `chmod` to change permissions.
- Use `chown` to change file ownership.
- Use `chgrp` to change a file's group.
- Identify common permission values such as `644`, `755`, and `600`.
