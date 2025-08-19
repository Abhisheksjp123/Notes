# Shell scripting
Shell scripting refers to writing scripts that run in a command-line shell environment. A shell is a program that interprets and executes commands, acting as an interface between you and the operating system. Shell scripts are collections of commands written in a text file that can be executed sequentially.

**Shell vs Bash:**

- **Shell** is the generic term for command-line interpreters (like sh, bash, zsh, fish, csh)
- **Bash** (Bourne Again Shell) is a specific type of shell - one of the most popular Unix/Linux shells
- Bash is backward-compatible with the original Bourne shell (sh) but includes additional features like command completion, history, and improved scripting capabilities
- Other shells have different syntax and features, but bash has become the default on most Linux distributions


# Common Shell Commands 
## Directory Navigation

### Change Directory (cd)

bash
```bash
cd /path/to/directory    # Change to absolute path
cd ../                   # Go up one directory (parent)
cd ~                     # Go to home directory
cd -                     # Go to previous directory
cd                       # Go to home directory (shortcut)
cd ../../                # Go up two directories
```

### List Directory Contents (ls)

bash

```bash
ls                       # List files and directories
ls -l                    # Long format with details
ls -la                   # Include hidden files with details
ls -lh                   # Human readable file sizes
```

## File Operations

### Create/Remove

bash

```bash
touch filename           # Create empty file
mkdir dirname           # Create directory
mkdir -p path/to/dir    # Create nested directories
rm filename             # Remove file
rm -r dirname           # Remove directory recursively
rm -rf dirname          # Force remove directory
```

### Copy/Move

bash

```bash
cp source destination    # Copy file
cp -r source dest       # Copy directory recursively
mv source destination   # Move/rename file or directory
```

## File Viewing/Editing

bash

```bash
cat filename            # Display entire file
head filename           # Show first 10 lines
tail filename           # Show last 10 lines
tail -f filename        # Follow file changes (logs)
less filename           # View file page by page
grep "pattern" file     # Search for pattern in file
```

## Process Management

bash

```bash
ps aux                  # List all running processes
kill PID                # Terminate process by ID
killall processname     # Kill all processes by name
jobs                    # Show active jobs
nohup command &         # Run command in background
```

## System Information

bash

```bash
pwd                     # Print current directory
whoami                  # Current user
df -h                   # Disk space usage
free -h                 # Memory usage
top                     # Real-time system monitor
```

---
# Python Terminal Commands

