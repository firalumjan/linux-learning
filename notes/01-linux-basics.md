# Linux Basics

## Learning Objectives

By the end of this lesson, you will be able to:

- Explain what Linux is.
- Describe the role of an Operating System.
- Differentiate between the Kernel, Shell, Terminal, and Distribution.
- Identify common Linux distributions.
- Use basic Linux information commands.

---

## What is Linux?

Linux is an **open-source operating system kernel** created by **Linus Torvalds** in **1991**.

Today, Linux powers:

- Servers
- Cloud computing
- Android devices
- Supercomputers
- Embedded systems
- Desktop computers

---

## What is an Operating System?

An **Operating System (OS)** is software that acts as an interface between the **user** and the **computer hardware**.

Examples:

- Linux
- Windows
- macOS

Responsibilities:

- Process management
- Memory management
- File management
- Device management
- Security

---

## Memory Trick

Think of a computer like a restaurant:

```text
User      → Customer
Shell     → Waiter
Kernel    → Chef
Hardware  → Kitchen
```

The customer (User) tells the waiter (Shell) what they want.

The waiter sends the request to the chef (Kernel).

The chef uses the kitchen (Hardware) to prepare the result.

---

## Linux Architecture

```text
+------------------+
|      User        |
+------------------+
         |
         v
+------------------+
|      Shell       |
+------------------+
         |
         v
+------------------+
|     Kernel       |
+------------------+
         |
         v
+------------------+
|    Hardware      |
+------------------+
```

---

## Linux Distribution (Distro)

A **Linux Distribution** combines:

- Linux Kernel
- Software Packages
- Utilities
- Package Manager
- Desktop Environment (optional)

Popular Linux distributions:

| Distribution | Common Use |
|--------------|------------|
| Ubuntu | Beginners, Servers |
| Debian | Stable Servers |
| Fedora | Developers |
| Arch Linux | Advanced Users |
| Rocky Linux | Enterprise Servers |
| Kali Linux | Penetration Testing |

---

## Ubuntu

Ubuntu is a Debian-based Linux distribution maintained by **Canonical**.

Features:

- Beginner friendly
- Large community support
- Uses the APT package manager
- Popular for servers and desktops
- Free and open source

---

## Linux Kernel

The **Kernel** is the core component of Linux.

Responsibilities:

- CPU scheduling
- Memory management
- Process management
- Device communication
- Hardware control

Check the kernel version:

```bash
uname -r
```

View detailed system information:

```bash
uname -a
```

---

## Shell

A **Shell** is a command-line interpreter.

It accepts commands from the user and passes them to the kernel.

Common shells:

- Bash
- Zsh
- Fish
- Sh

Check your current shell:

```bash
echo $SHELL
```

---

## Terminal

A **Terminal** is the application used to access the shell.

Examples:

- GNOME Terminal
- Konsole
- XTerm

> **Remember:**  
> Terminal = Application  
> Shell = Command Interpreter

---

## Important Commands

### Current user

```bash
whoami
```

### Current directory

```bash
pwd
```

### Computer hostname

```bash
hostname
```

### Current date and time

```bash
date
```

### Kernel version

```bash
uname -r
```

### Detailed system information

```bash
uname -a
```

### Command history

```bash
history
```

### Clear the terminal

```bash
clear
```

### Current shell

```bash
echo $SHELL
```

---

## Useful Command Variations

View complete system information:

```bash
hostnamectl
```

View the manual page for a command:

```bash
man pwd
```

General syntax:

```bash
man <command>
```

Example:

```bash
man ls
```

---

## Useful Keyboard Shortcuts

| Shortcut | Description |
|----------|-------------|
| Ctrl + C | Stop a running command |
| Ctrl + L | Clear the terminal |
| Ctrl + R | Search command history |
| Tab | Auto-complete commands and filenames |
| Up Arrow | Previous command |
| Down Arrow | Next command |

---

## Command Cheat Sheet

| Command | Purpose |
|----------|---------|
| whoami | Display current user |
| pwd | Show current directory |
| hostname | Display computer name |
| hostnamectl | Detailed system information |
| date | Show current date and time |
| uname -r | Show kernel version |
| uname -a | Show complete system information |
| echo $SHELL | Display current shell |
| history | Show command history |
| clear | Clear terminal screen |

---

## Where Linux Is Used

Linux is widely used in:

- Web servers
- Cloud platforms (AWS, Azure, GCP)
- Android devices
- Supercomputers
- IoT devices
- Cybersecurity
- DevOps
- Docker containers
- Kubernetes clusters

---

## Practice

Run each command and observe its output.

```bash
whoami
pwd
hostname
hostnamectl
date
uname -r
uname -a
history
echo $SHELL
```

---

## Interview Questions

### What is Linux?

Linux is an open-source operating system kernel created by Linus Torvalds in 1991.

---

### What is an Operating System?

An Operating System manages hardware resources and provides an interface between users and hardware.

---

### What is the difference between Linux and Ubuntu?

Linux is the kernel.

Ubuntu is a Linux distribution built around the Linux kernel.

---

### What is the Kernel?

The Kernel is the core component of an operating system responsible for managing hardware resources, memory, processes, and devices.

---

### What is the difference between a Shell and a Terminal?

- **Shell:** A command interpreter that executes user commands.
- **Terminal:** An application used to access the shell.

---

### What is a Linux Distribution?

A Linux distribution is a complete operating system built using the Linux kernel along with software packages and utilities.

---

## Key Takeaways

- Linux is an open-source operating system kernel.
- Ubuntu is a Linux distribution.
- The Kernel manages hardware resources.
- The Shell interprets user commands.
- The Terminal provides access to the shell.
- Linux is widely used in servers, cloud computing, DevOps, and embedded systems.
- Basic commands help you identify system information and navigate your Linux environment.

---

## Summary

After completing this lesson, you should understand:

- What Linux is
- What an Operating System does
- What a Linux Distribution is
- What Ubuntu is
- The role of the Linux Kernel
- The difference between a Shell and a Terminal
- Basic Linux system information commands
- Common keyboard shortcuts
- Real-world applications of Linux
