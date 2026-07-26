# Linux Basics

## What is Linux?

Linux is an open-source operating system kernel created by Linus Torvalds in 1991. It is widely used in servers, cloud computing, embedded systems, Android devices, and desktop computers.

---

## What is an Operating System?

An Operating System (OS) is software that acts as an interface between the user and the computer hardware.

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

## Linux Distribution (Distro)

A Linux distribution combines the Linux kernel with software packages, utilities, and a package manager.

Examples:
- Ubuntu
- Debian
- Fedora
- Arch Linux
- Rocky Linux
- Kali Linux

---

## Ubuntu

Ubuntu is a Debian-based Linux distribution maintained by Canonical.

Features:
- Beginner friendly
- Large community support
- Uses the APT package manager
- Commonly used for servers and desktops

---

## Linux Kernel

The kernel is the core component of Linux.

Responsibilities:
- CPU scheduling
- Memory management
- Device communication
- Process management

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

A shell is a command-line interpreter that accepts commands from the user and passes them to the kernel.

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

The terminal is the application used to interact with the shell.

Examples:
- GNOME Terminal
- Konsole
- XTerm

---

## Important Commands

Current user:

```bash
whoami
```

Current directory:

```bash
pwd
```

Hostname:

```bash
hostname
```

Current date:

```bash
date
```

Kernel version:

```bash
uname -r
```

Detailed system information:

```bash
uname -a
```

Command history:

```bash
history
```

Clear the terminal:

```bash
clear
```

---

## Practice

Run the following commands and observe their output:

```bash
whoami
pwd
hostname
date
uname -r
uname -a
history
echo $SHELL
```

---

## Summary

After completing this topic, you should understand:

- What Linux is
- What an operating system does
- What a Linux distribution is
- What Ubuntu is
- The role of the Linux kernel
- The difference between a shell and a terminal
- Basic information commands
