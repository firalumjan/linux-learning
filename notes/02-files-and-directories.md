# Files and Directories

## Learning Objectives

By the end of this lesson, you will be able to:

- Understand files and directories in Linux.
- Navigate the Linux file system.
- Differentiate between absolute and relative paths.
- Create, copy, move, rename, and delete files and directories.
- Search for files using the `find` command.
- Use common Linux file management commands confidently.

---

## What is a File?

A **file** is a collection of data stored on a computer.

Examples:

- report.pdf
- notes.txt
- photo.jpg
- script.sh

---

## What is a Directory?

A **directory** (folder) is used to organize files and other directories.

Example:

```text
Documents/
├── Resume.pdf
├── Notes.txt
└── Projects/
```

---

## Memory Trick

Think of your computer like a filing cabinet.

- Directory = Folder
- File = Document

```text
Cabinet
│
├── Folder (Directory)
│   ├── Resume.pdf
│   ├── Notes.txt
│   └── Photo.jpg
```

Directories organize files just like folders organize papers.

---

# Linux File System Hierarchy

Everything in Linux starts from the **Root Directory** (`/`).

```text
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

---

## Important Directories

| Directory | Purpose |
|------------|---------|
| `/` | Root directory |
| `/home` | User home directories |
| `/etc` | System configuration files |
| `/usr` | User applications and libraries |
| `/var` | Logs and variable data |
| `/tmp` | Temporary files |
| `/boot` | Boot loader files |
| `/dev` | Device files |
| `/proc` | Process information |
| `/root` | Home directory of the root user |

---

# Absolute vs Relative Paths

## Absolute Path

Starts from the **root directory (`/`)**.

Example:

```text
/home/najmul-arif/linux-learning
```

It always begins with `/`.

---

## Relative Path

Starts from your **current working directory**.

Example:

```text
notes/
practice/docs/
```

It does **not** begin with `/`.

---

## Memory Trick

**Absolute = Full Address**

Like:

```text
House No. 45,
Main Road,
Hyderabad
```

**Relative = Nearby Direction**

Like:

```text
Go to the next room.
```

---

# Directory Navigation Diagram

```text
/
└── home
    └── najmul-arif
        └── linux-learning
            ├── notes
            ├── practice
            └── README.md
```

---

# Essential Commands

## Print Working Directory

```bash
pwd
```

Displays your current directory.

---

## List Files

```bash
ls
```

Detailed list:

```bash
ls -l
```

Include hidden files:

```bash
ls -la
```

Human-readable sizes:

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

## Create Files

```bash
touch notes.txt
```

Multiple files:

```bash
touch file1.txt file2.txt file3.txt
```

---

## Copy

Copy a file:

```bash
cp file1.txt backup.txt
```

Copy a directory recursively:

```bash
cp -r project backup
```

---

## Move or Rename

Move:

```bash
mv file.txt Documents/
```

Rename:

```bash
mv old.txt new.txt
```

---

## Remove Files

Delete a file:

```bash
rm file.txt
```

Delete a directory recursively:

```bash
rm -r folder
```

---

# Wildcards

All text files:

```bash
*.txt
```

One character:

```bash
file?.txt
```

Character range:

```bash
file[1-5].txt
```

Examples:

```bash
ls *.txt
rm *.log
cp *.jpg images/
```

---

# Find Files

Search for all text files:

```bash
find . -name "*.txt"
```

Search for a specific file:

```bash
find . -name "notes.txt"
```

Search from the home directory:

```bash
find ~/ -name "*.pdf"
```

---

# Practice Lab

Run the following commands:

```bash
mkdir practice
cd practice

touch file1.txt
touch file2.txt

mkdir docs

cp file1.txt docs/

mv file2.txt notes.txt

find . -name "*.txt"

ls -la

pwd
```

Observe the directory structure after each command.

---

# Command Cheat Sheet

| Command | Description |
|----------|-------------|
| pwd | Show current directory |
| ls | List files |
| ls -l | Long listing |
| ls -la | Show hidden files |
| ls -lh | Human-readable sizes |
| cd | Change directory |
| mkdir | Create directory |
| rmdir | Remove empty directory |
| touch | Create file |
| cp | Copy files |
| cp -r | Copy directories |
| mv | Move or rename |
| rm | Remove file |
| rm -r | Remove directory recursively |
| find | Search for files |

---

# Interview Questions

### What is the difference between a file and a directory?

A file stores data, while a directory stores files and other directories.

---

### What is the difference between an absolute path and a relative path?

An absolute path starts from the root directory (`/`).

A relative path starts from the current working directory.

---

### Which command copies directories?

```bash
cp -r
```

---

### Which command renames a file?

```bash
mv
```

---

### What does this command do?

```bash
find . -name "*.txt"
```

Searches for all files ending with the `.txt` extension in the current directory and its subdirectories.

---

### What is the difference between:

```bash
rm file.txt
```

and

```bash
rm -r folder
```

- `rm file.txt` deletes a file.
- `rm -r folder` deletes a directory and all of its contents recursively.

---

# Key Takeaways

- Everything in Linux starts from the root directory (`/`).
- Directories organize files.
- Absolute paths always begin with `/`.
- Relative paths begin from your current location.
- `cp` copies files and directories.
- `mv` moves or renames files.
- `rm` deletes files.
- `rm -r` deletes directories recursively.
- `find` searches for files and directories.

---

# Summary

After completing this lesson, you should understand:

- Files and directories
- Linux file system hierarchy
- Absolute and relative paths
- File management commands
- Wildcards
- The `find` command
- Basic file system navigation
- Practical Linux file operations
