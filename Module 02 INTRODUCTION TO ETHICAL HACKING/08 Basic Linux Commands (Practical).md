# Basic Linux Commands

Linux commands are used to perform various tasks in the terminal or command line interface. Here's a list of essential commands for navigating and managing files in Linux.

## File and Directory Operations

### 1. **`ls`**
   - **Description**: Lists files and directories in the current directory.
   - **Usage**: `ls [options] [path]`
   - **Examples**: 
     - `ls` – Lists files and directories.
     - `ls -l` – Lists with detailed information.
     - `ls -a` – Lists all files, including hidden ones.

### 2. **`cd`**
   - **Description**: Changes the current directory.
   - **Usage**: `cd [directory]`
   - **Examples**: 
     - `cd /home/user` – Changes to `/home/user`.
     - `cd ..` – Moves up one directory level.

### 3. **`pwd`**
   - **Description**: Prints the current working directory.
   - **Usage**: `pwd`
   - **Example**: 
     - `pwd` – Displays the full path of the current directory.

### 4. **`mkdir`**
   - **Description**: Creates a new directory.
   - **Usage**: `mkdir [directory]`
   - **Examples**: 
     - `mkdir newfolder` – Creates a directory named `newfolder`.
     - `mkdir -p parent/child` – Creates nested directories.

### 5. **`rmdir`**
   - **Description**: Removes an empty directory.
   - **Usage**: `rmdir [directory]`
   - **Example**: 
     - `rmdir oldfolder` – Removes the `oldfolder` directory if it's empty.

### 6. **`rm`**
   - **Description**: Removes files or directories.
   - **Usage**: `rm [options] [file]`
   - **Examples**: 
     - `rm file.txt` – Removes `file.txt`.
     - `rm -r folder` – Recursively removes `folder` and its contents.

### 7. **`cp`**
   - **Description**: Copies files or directories.
   - **Usage**: `cp [options] [source] [destination]`
   - **Examples**: 
     - `cp file.txt /home/user/` – Copies `file.txt` to `/home/user/`.
     - `cp -r folder1 folder2` – Copies `folder1` and its contents to `folder2`.

### 8. **`mv`**
   - **Description**: Moves or renames files or directories.
   - **Usage**: `mv [source] [destination]`
   - **Examples**: 
     - `mv file.txt /home/user/` – Moves `file.txt` to `/home/user/`.
     - `mv oldname.txt newname.txt` – Renames `oldname.txt` to `newname.txt`.

### 9. **`touch`**
   - **Description**: Creates an empty file or updates the timestamp of an existing file.
   - **Usage**: `touch [file]`
   - **Example**: 
     - `touch newfile.txt` – Creates an empty file named `newfile.txt`.

## Viewing and Editing Files

### 10. **`cat`**
   - **Description**: Concatenates and displays file content.
   - **Usage**: `cat [file]`
   - **Example**: 
     - `cat file.txt` – Displays the content of `file.txt`.

### 11. **`more`**
   - **Description**: Views file content one screen at a time.
   - **Usage**: `more [file]`
   - **Example**: 
     - `more file.txt` – Displays `file.txt` content page by page.

### 12. **`less`**
   - **Description**: Similar to `more`, but with additional features for navigating through the file.
   - **Usage**: `less [file]`
   - **Example**: 
     - `less file.txt` – Allows scrolling through `file.txt`.

### 13. **`head`**
   - **Description**: Displays the first few lines of a file.
   - **Usage**: `head [file]`
   - **Example**: 
     - `head file.txt` – Shows the first 10 lines of `file.txt`.

### 14. **`tail`**
   - **Description**: Displays the last few lines of a file.
   - **Usage**: `tail [file]`
   - **Example**: 
     - `tail file.txt` – Shows the last 10 lines of `file.txt`.

## System Information

### 15. **`df`**
   - **Description**: Displays disk space usage for file systems.
   - **Usage**: `df [options]`
   - **Example**: 
     - `df -h` – Shows disk usage in human-readable format.

### 16. **`du`**
   - **Description**: Displays disk usage of files and directories.
   - **Usage**: `du [options] [path]`
   - **Example**: 
     - `du -sh folder` – Shows the total size of `folder`.

### 17. **`top`**
   - **Description**: Displays real-time system processes and resource usage.
   - **Usage**: `top`
   - **Example**: 
     - `top` – Opens the interactive process viewer.

### 18. **`ps`**
   - **Description**: Displays information about active processes.
   - **Usage**: `ps [options]`
   - **Example**: 
     - `ps aux` – Shows detailed information about all running processes.

### 19. **`uname`**
   - **Description**: Displays system information.
   - **Usage**: `uname [options]`
   - **Example**: 
     - `uname -a` – Shows all available system information.

### 20. **`shutdown`**
   - **Description**: Shuts down or reboots the system.
   - **Usage**: `shutdown [options]`
   - **Examples**: 
     - `shutdown -h now` – Immediately shuts down the system.
     - `shutdown -r now` – Reboots the system immediately.

## Summary

These basic Linux commands provide fundamental tools for managing files, directories, and system operations. Mastering these commands will help you navigate and control your Linux environment more effectively.
