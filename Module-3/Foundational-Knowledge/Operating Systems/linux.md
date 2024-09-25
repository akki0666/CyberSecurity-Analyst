# Creating a markdown file with the provided content and proper highlighting

markdown_content = """
# Linux: Comprehensive Guide

## Table of Contents
1. **Command-Line Basics**
   - 1.1 The Terminal
   - 1.2 Basic Commands
   - 1.3 Viewing File Contents
   - 1.4 Searching for Files
   - 1.5 System Information

2. **File Permissions**
   - 2.1 Understanding Permissions
   - 2.2 Permission Structure
   - 2.3 Changing Permissions
   - 2.4 Ownership

3. **Scripting**
   - 3.1 Shell Scripting Basics
   - 3.2 Script Structure
   - 3.3 Variables
   - 3.4 Control Structures
   - 3.5 Functions
   - 3.6 Input/Output
   - 3.7 Error Handling

4. **Deep Dive into Topics**
   - 4.1 Advanced Command-Line Usage
   - 4.2 Regular Expressions
   - 4.3 Environment Variables
   - 4.4 Networking Commands
   - 4.5 System Administration Commands

---

## 1. Command-Line Basics

### 1.1 The Terminal
- **Definition**: The terminal is a command-line interface that allows users to interact with the operating system using text-based commands.
- **Accessing the Terminal**: 
  - On most Linux distributions, you can open the terminal through the applications menu or by using keyboard shortcuts (e.g., `Ctrl + Alt + T`).

### 1.2 Basic Commands
- **Navigation Commands**:
  - `pwd`: Displays the current working directory.
  - `cd [directory]`: Changes the current directory.
    - Example: `cd Documents` changes to the Documents directory.
    - `cd ..`: Moves up one directory level.
  - `ls`: Lists files and directories in the current directory.
    - `ls -l`: Lists files with detailed information (permissions, ownership, size, date).
    - `ls -a`: Shows hidden files (those beginning with a dot).

- **File Operations**:
  - `touch [file]`: Creates an empty file or updates the timestamp of an existing file.
  - `mkdir [directory]`: Creates a new directory.
    - Example: `mkdir new_folder`.
  - `cp [source] [destination]`: Copies files or directories.
    - Example: `cp file.txt /home/user/backup/`.
    - Use `-r` to copy directories recursively: `cp -r dir1 dir2`.
  - `mv [source] [destination]`: Moves or renames files or directories.
    - Example: `mv old_name.txt new_name.txt`.
  - `rm [file]`: Deletes files.
    - Example: `rm file.txt`.
    - Use `-r` for directories: `rm -r directory_name`.
    - Use `-f` to force deletion without prompts: `rm -f file.txt`.

### 1.3 Viewing File Contents
- **cat**: Displays the entire content of a file.
  - Example: `cat file.txt`.
- **less**: Views file content page by page, allowing scrolling.
  - Example: `less file.txt`.
- **head**: Shows the first 10 lines of a file.
  - Example: `head file.txt`.
  - Use `head -n [number]` to specify the number of lines.
- **tail**: Displays the last 10 lines of a file.
  - Example: `tail file.txt`.
  - Use `-n` for more lines or `-f` to follow real-time updates.
  - Example: `tail -f logfile.txt` to monitor a log file.

### 1.4 Searching for Files
- `find [path] -name [filename]`: Searches for files by name.
  - Example: `find /home/user -name "*.txt"` searches for all text files in the user's home directory.
- `grep [pattern] [file]`: Searches for a pattern within a file.
  - Example: `grep "error" logfile.txt` searches for the word "error" in `logfile.txt`.

### 1.5 System Information
- `uname -a`: Displays system information, including the kernel name, version, and architecture.
- `top`: Shows running processes in real-time.
- `df -h`: Displays disk space usage in human-readable format.
- `free -h`: Displays memory usage (RAM) in human-readable format.

---

## 2. File Permissions

### 2.1 Understanding Permissions
- **Types of Permissions**:
  - **Read (r)**: Allows reading the contents of a file or listing files in a directory.
  - **Write (w)**: Allows modifying a file or creating/deleting files in a directory.
  - **Execute (x)**: Allows executing a file as a program or accessing a directory.

### 2.2 Permission Structure
- Permissions are represented as a string of 10 characters:
  - Example: `drwxr-xr-x`
    - **First character**: Indicates the type (d for directory, - for regular file).
    - **Next three characters**: Owner permissions (rwx).
    - **Next three characters**: Group permissions (r-x).
    - **Last three characters**: Other users’ permissions (r-x).

### 2.3 Changing Permissions
- **chmod**: Changes file permissions.
  - **Numeric Method**: Use numbers to represent permissions.
    - `chmod 755 [file]`:
      - Owner: read, write, execute (7)
      - Group: read, execute (5)
      - Others: read, execute (5)
  - **Symbolic Method**: Use letters to specify permissions.
    - `chmod u+x [file]`: Adds execute permission for the user (owner).
    - `chmod g-w [file]`: Removes write permission for the group.

### 2.4 Ownership
- **Changing Ownership**:
  - `chown [owner]:[group] [file]`: Changes the owner and group of a file.
    - Example: `chown user:group file.txt`.
- **Viewing Ownership**:
  - `ls -l`: Displays the owner and group of files.

---

## 3. Scripting

