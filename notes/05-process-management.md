# Process Management

## What is a Process?

A **process** is a program that is currently running in memory.

Examples:
- Firefox browser
- Bash shell
- VS Code
- `sleep` command

---

## Program vs Process

| Program | Process |
|----------|---------|
| Stored on disk | Running in RAM |
| Passive | Active |
| Does not consume CPU | Uses CPU and memory |

### Memory Trick

> **Program = Disk** 💾
>
> **Process = RAM** 🧠

---

# Process IDs

Every running process has a unique identifier.

## PID (Process ID)

A **PID** uniquely identifies a running process.

Display the current shell's PID:

```bash
echo $$
```

---

## PPID (Parent Process ID)

A **PPID** identifies the parent process that started the current process.

Display the parent process ID:

```bash
echo $PPID
```

---

# Viewing Processes

## ps

Displays a snapshot of the processes associated with the current terminal.

```bash
ps
```

Show all running processes in full-format:

```bash
ps -ef
```

Show all processes with CPU and memory usage (BSD format):

```bash
ps aux
```

---

## Difference Between `ps`, `ps -ef`, and `ps aux`

| Command | Description |
|----------|-------------|
| `ps` | Shows processes for the current terminal |
| `ps -ef` | Shows all running processes in full-format |
| `ps aux` | Shows all processes with CPU, memory, user, and command information |

---

## top

Displays live system and process information.

```bash
top
```

Useful information displayed:

- CPU usage
- Memory usage
- Running processes
- Process IDs
- System load

Exit:

```text
q
```

---

## htop

A more interactive and user-friendly version of `top`.

Install:

```bash
sudo apt install htop
```

Run:

```bash
htop
```

Exit:

```text
q
```

---

# Process States

Processes can exist in different states.

| State | Meaning |
|--------|---------|
| R | Running |
| S | Sleeping |
| T | Stopped |
| Z | Zombie |

View process states:

```bash
ps aux
```

---

# Background Jobs

## sleep

The `sleep` command pauses execution for a specified number of seconds.

Example:

```bash
sleep 300
```

This pauses for **300 seconds (5 minutes)**.

Run it in the background:

```bash
sleep 300 &
```

---

## jobs

Display background jobs:

```bash
jobs
```

Example:

```bash
sleep 300 &
sleep 500 &
jobs
```

Output:

```text
[1]- Running  sleep 300 &
[2]+ Running  sleep 500 &
```

---

# Foreground and Background

Move a stopped job to the background:

```bash
bg
```

Resume a specific job:

```bash
bg %2
```

Bring a background job to the foreground:

```bash
fg
```

Bring a specific job to the foreground:

```bash
fg %1
```

---

# Signals

## kill

Terminate a process gracefully.

```bash
kill PID
```

`kill` sends the **SIGTERM (15)** signal, allowing the process to close cleanly.

---

## kill -9

Forcefully terminate a process.

```bash
kill -9 PID
```

`kill -9` sends the **SIGKILL (9)** signal, immediately stopping the process without allowing cleanup.

> ⚠️ Use `kill -9` only when a normal `kill` does not work.

---

# Keyboard Shortcuts

| Shortcut | Action |
|----------|--------|
| **Ctrl + C** | Terminates the running foreground process |
| **Ctrl + Z** | Suspends (pauses) the running process |

Resume the suspended process:

Background:

```bash
bg
```

Foreground:

```bash
fg
```

---

# Process Priority

Linux schedules processes using priorities.

Nice values range from:

- **-20** → Highest priority
- **0** → Default priority
- **19** → Lowest priority

Start a process with lower priority:

```bash
nice -n 10 sleep 300
```

> Lower nice value = Higher priority
>
> Higher nice value = Lower priority

---

# Common Commands

Current shell PID:

```bash
echo $$
```

Parent shell PID:

```bash
echo $PPID
```

Current user:

```bash
whoami
```

View processes:

```bash
ps
```

Show all processes:

```bash
ps -ef
```

Detailed process information:

```bash
ps aux
```

Live process monitor:

```bash
top
```

Interactive process monitor:

```bash
htop
```

Background jobs:

```bash
jobs
```

Terminate process:

```bash
kill PID
```

Force terminate:

```bash
kill -9 PID
```

---

# Practice Lab

```bash
mkdir ~/linux-learning/labs/day5

cd ~/linux-learning/labs/day5

ps

ps -ef

ps aux

top

sleep 300 &

jobs

fg

# Press Ctrl + Z

bg

jobs

kill PID

sleep 300 &

kill -9 PID

echo $$

echo $PPID

nice -n 10 sleep 300
```

---

# Command Summary

| Command | Description |
|----------|-------------|
| `ps` | Display running processes |
| `ps -ef` | Show all processes |
| `ps aux` | Detailed process list |
| `top` | Live process monitor |
| `htop` | Interactive process monitor |
| `jobs` | Show background jobs |
| `bg` | Resume a stopped job in the background |
| `fg` | Bring a background job to the foreground |
| `kill` | Gracefully terminate a process |
| `kill -9` | Forcefully terminate a process |
| `nice` | Start a process with a lower priority |
| `echo $$` | Display current shell PID |
| `echo $PPID` | Display parent process ID |

---

# Interview Questions

1. What is a process?
2. What is the difference between a program and a process?
3. What is PID?
4. What is PPID?
5. What is the difference between `ps`, `ps -ef`, and `ps aux`?
6. What is the difference between `top` and `htop`?
7. What does the `jobs` command display?
8. What does the `kill` command do?
9. What is the difference between `kill` and `kill -9`?
10. What does **Ctrl + C** do?
11. What does **Ctrl + Z** do?
12. What does the `bg` command do?
13. What does the `fg` command do?
14. What is the purpose of the `nice` command?
15. What is the difference between a foreground process and a background process?

---

# Summary

After completing this lesson, you should be able to:

- Explain what a process is.
- Differentiate between a program and a process.
- Identify PID and PPID.
- View running processes using `ps`, `top`, and `htop`.
- Understand process states.
- Manage foreground and background jobs.
- Terminate processes using `kill` and `kill -9`.
- Understand Linux process priorities using `nice`.
- Perform basic process management tasks from the command line.
