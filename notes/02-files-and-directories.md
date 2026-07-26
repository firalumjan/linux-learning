# Files and Directories

## What is a File?

A file is a collection of data stored on the computer.

Examples:
- report.pdf
- notes.txt
- photo.jpg
- script.sh

---

## What is a Directory?

A directory (folder) is used to organize files and other directories.

Example:

```
Documents/
├── Resume.pdf
├── Notes.txt
└── Projects/
```

---

# Linux File System Hierarchy

Everything in Linux starts from the **root directory**.

```
/
├── bin
├── boot
├── dev
├── etc
├── home
├── lib
├── media
├── mnt
├── opt
├── proc
├── root
├── run
├── sbin
├── srv
├── sys
├── tmp
├── usr
└── var
```

### Important Directories

| Directory | Purpose |
|------------|---------|
| `/` | Root directory |
| `/home` | User home directories |
| `/etc` | System configuration files |
| `/var` | Logs and variable data |
| `/usr` | User applications and libraries |
| `/tmp` | Temporary files |
| `/boot` | Boot loader files |
| `/dev` | Device files |
| `/proc` | Process information |
| `/root` | Home directory of the root user |

---

# Absolute vs Relative Paths

### Absolute Path

Starts from `/`

Example:

```
/home/najmul-arif/linux-learning
```

### Relative Path

Starts from the current directory.

Example:

```
notes/
```

---

# Essential Commands

## Print Working Directory

```bash
pwd
```

Shows your current location.

---

## List Files

```bash
ls
```

Detailed list:

```bash
ls -l
```

Show hidden files:

```bash
ls -la
```

Human-readable file sizes:

```bash
ls -lh
```

---

## Change Directory

```bash
cd
```

Examples:

```bash
cd /home
cd ~
cd ..
cd -
```

---

## Create Directory

```bash
mkdir test
```

Create multiple directories:

```bash
mkdir project1 project2 project3
```

---

## Remove Empty Directory

```bash
rmdir test
```

---

## Create File

```bash
touch notes.txt
```

---

## Copy

Copy a file:

```bash
cp file1.txt file2.txt
```

Copy a directory:

```bash
cp -r project backup
```

---

## Move / Rename

Move:

```bash
mv file.txt Documents/
```

Rename:

```bash
mv old.txt new.txt
```

---

## Remove

Delete a file:

```bash
rm file.txt
```

Delete a directory:

```bash
rm -r folder
```

---

# Wildcards

All text files:

```bash
*.txt
```

Any one character:

```bash
file?.txt
```

Character ranges:

```bash
file[1-5].txt
```

---

# Find Files

```bash
find . -name "*.txt"
```

---

# Command Summary

| Command | Description |
|----------|-------------|
| pwd | Show current directory |
| ls | List files |
| ls -la | Show hidden files |
| cd | Change directory |
| mkdir | Create directory |
| rmdir | Remove empty directory |
| touch | Create file |
| cp | Copy files/directories |
| mv | Move or rename |
| rm | Delete files |
| rm -r | Delete directories |
| find | Search for files |

---

# Summary

After completing this topic, you should be able to:

- Navigate directories
- Create files and folders
- Copy files
- Rename files
- Delete files
- Search for files
- Understand absolute and relative paths
