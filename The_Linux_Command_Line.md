# The Linux Command Line: a complete introduction (notes)
## 0 Cursor Movement Commands
- Ctrl-a Move cursor to the beginning of the line.
- Ctrl-e Move cursor to the end of the line.
- Ctrl-f Move cursor forward one character; same as the right arrow key.
- Ctrl-b Move cursor backward one character; same as the left arrow key.
- Ctrl-l Clear the screen and move the cursor to the top left corner. The clear command does the same thing.
- Ctrl-d Delete the character at the cursor location
- Ctrl-k Kill text from the cursor location to the end of line.
- Ctrl-u Kill text from the cursor location to the beginning of the line.

## 1 What Is The Shell?

## 2 Navigation
- **pwd** - Print name of current working directory
- **cd** - Change directory
- **ls** - List directory contents

## 3 Exploring The System
- **ls** - List directory contents
- **file** - Determine file type
- **less** - View file contents

## 4 Manipulating Files And Directories
- **cp** - Copy files and directories
- **mv** - Move/rename files and directories
- **mkdir** - Create directories
- **rm** - Remove files and directories
- **ln** - Create hard and symbolic links
 
## 5 Working With Commands
- **type** - Indicate how a command name is interpreted
- **which** - Display which **executable program** will be executed
- **help** - Get help for **shell builtins**
- **man** - Display a command's manual page
- **apropos** - Display a list of appropriate commands
- **info** - Display a command's info entry
- **whatis** - Display a very brief description of a command
- **alias** - Create an **alias** for a command

## 6 Redirection
- **cat** - Concatenate files
- **sort** - Sort lines of text
- **uniq** - Report or omit repeated lines
- **grep** - Print lines matching a pattern
- **wc** - Print newline, word, and byte counts for each file
- **head** - Output the first part of a file
- **tail** - Output the last part of a file
- **tee** - Read from standard input and write to standard output and files

## 7 Seeing The World As The Shell Sees It
- **echo** - Display a line of text

## 8 Advanced Keyboard Tricks
- **clear** - Clear the screen
- **history** - Display the contents of the history list

## 9 Permissions
- **id** - Display user identity
- **chmod** - Change a file's mode
- **umask** - Set the default file permissions
- **su** - Run a shell as another user
- **sudo** - Execute a command as another user
- **chown** - Change a file's owner
- **chgrp** - Change a file's group ownership
- **passwd** - Change a user's password

## 10 Processes
- **ps** - Report a snapshot of current processes
- **top** - Display tasks
- **jobs** - List active jobs
- **bg** - Place a job in the background
- **fg** - Place a job in the foreground
- **kill** - Send a signal to a process
- **killall** - Kill processes by name
- **shutdown** - Shutdown or reboot the system

## 11 The Environment
- **printenv** - Print part or all of the environment
- **set** - Set shell options
- **export** - Export environment to subsequently executed programs
- **alias** - Create an alias for a command

## 12 A Gentle Introduction To vi

## 13 Customizing The Prompt

## 14 Package Management

## 15 Storage Media
- **mount** - Mount a file system
- **umount** - Unmount a file system
- **fsck** - Check and repair a file system
- **fdisk** - Partition table manipulator
- **mkfs** - Create a file system
- **fdformat** - Format a floppy disk
- **dd** - Write block oriented data directly to a device
- **genisoimage** (mkisofs) - Create an ISO 9660 image file
- **wodim** (cdrecord) - Write data to optical storage media
- **md5sum** - Calculate an MD5 checksum

## 16 Networking
- **ping** - Send an ICMP ECHO\_REQUEST to network hosts
- **traceroute** - Print the route packets trace to a network host
- **netstat** - Print network connections, routing tables, interface statistics, masquerade connections, and multicast memberships
- **ftp** - Internet file transfer program
- **wget** - Non-interactive network downloader
- **ssh** - OpenSSH SSH client (remote login program)
- **IP** (Internet Protocol) address
- **Host** and domain name
- **URI** (Uniform Resource Identifier)

## 17 Searching For Files
- **locate** - Find files by name
- **find** - Search for files in a directory hierarchy
- **xargs** - Build and execute command lines from standard input
- **touch** - Change file times
- **stat** - Display file or file system status

## 18 Archiving And Backup
- **gzip** - Compress or expand files
- **bzip2** - A block sorting file compressor
- **tar** - Tape archiving utility
- **zip** - Package and compress files
- **rsync** - Remote file and directory synchronization

## 19 Regular Expressions

## 20 Text Processing
- **cat** - Concatenate files and print on the standard output
- **sort** - Sort lines of text files
- **uniq** - Report or omit repeated lines
- **cut** - Remove sections from each line of files
- **paste** - Merge lines of files
- **join** - Join lines of two files on a common field
- **comm** - Compare two sorted files line by line
- **diff** - Compare files line by line
- **patch** - Apply a diff file to an original
- **tr** - Translate or delete characters
- **sed** - Stream editor for filtering and transforming text
- **aspell** - Interactive spell checker

## 21 Formatting Output
- **nl** - Number lines
- **fold** - Wrap each line to a specified length
- **fmt** - A simple text formatter
- **pr** - Prepare text for printing
- **printf** - Format and print data
- **groff** - A document formatting system

## 22 Printing
- **pr** - Convert text files for printing
- **lpr** - Print files
- **a2ps** - Format files for printing on a PostScript printer
- **lpstat** - Show printer status information
- **lpq** - Show printer queue status
- **lprm** - Cancel print jobs

## 23 Compiling Programs

## 24-36 Writing Shell Scripts
