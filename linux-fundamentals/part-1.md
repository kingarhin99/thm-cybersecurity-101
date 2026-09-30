[part 1.md](https://github.com/user-attachments/files/32862504/part.1.md)
# Linux Fundamentals (Part 1)

**Module:** Linux Fundamentals
**Status:** Completed

## What this room covers

My first time running commands in a Linux terminal: moving around the filesystem, reading files, searching for things, and combining commands with shell operators.

## Key concepts

- **Linux is everywhere:** most servers, cloud machines, and security tools run on Linux, so being comfortable in the terminal is a core skill.
- **The terminal (shell):** a text interface where you type commands instead of clicking. Many servers have no graphical interface, so this is often the only way in.
- **Working directory:** the folder you're currently "in." Commands run relative to it unless you give a full path.

## Commands I used

| Command | What it does | Example |
|---|---|---|
| `echo` | Prints text to the terminal | `echo "Hello"` |
| `whoami` | Shows which user I'm logged in as | `whoami` |
| `ls` | Lists files and folders in a directory | `ls` |
| `cd` | Changes directory | `cd Documents` |
| `cat` | Shows the contents of a file | `cat notes.txt` |
| `pwd` | Prints the full path of where I am | `pwd` |
| `find` | Searches for files by name or type | `find -name "*.txt"` |
| `grep` | Searches *inside* files for text | `grep "error" log.txt` |

## Shell operators

| Operator | What it does | Example |
|---|---|---|
| `&` | Runs a command in the background so I can keep using the terminal | `cp bigfile backup &` |
| `&&` | Runs the second command only if the first one succeeds | `cd folder && ls` |
| `>` | Sends output to a file, **overwriting** it | `echo hi > file.txt` |
| `>>` | Sends output to a file, **adding to the end** | `echo hi >> file.txt` |

## What tripped me up

At first I had trouble telling `find` and `grep` apart, since both "search" for something. What made it click:

- **`find` looks for files.** It searches by name, type, or location. Question: *"Where is the file called passwords.txt?"*
- **`grep` looks inside files.** It searches for text in a file's contents. Question: *"Which line in this file says 'password'?"*

An easy way to remember it: `find` is like searching for a book at the library, and `grep` is like searching for a word in the dictionary.

## How this connects to security

- `whoami` is one of the first things you run after getting into a system, to see what access you have.
- `find` and `grep` help locate interesting files like configs, logs, or passwords left in plain text. Defenders use the same tools to dig through logs.
- Mixing up `>` and `>>` can wipe a file, which matters a lot on a real system.
