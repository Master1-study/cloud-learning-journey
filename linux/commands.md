# Short notes on Linux
Linux commands have short and long options, if you type the short option you can use `-` and for a long option you can use `--`
## Command Structure

Most commands support multiple options that can modify their behavior

So it's command + -options arguments

### Single Dash

- a single Dash - is usually used for a short option 
- the can also be combined together
Example

```sh

ls -l # -l long listing format, it will show permissions, owner, size and date

ls -la # equivalent to
ls -l-a
# we have combined -l and -a and -a will show hidden files 

```

### Double dash

It is used for long options (full words, more descriptive)
### Example

```sh

rm --recursive folder_name 
# --rescursive same as -r
#This makes the command more readable especially for scripts

grep --ignore-case "pattern" file.text
# --ignore-case = ignore carpitalization
```

Single Dash = one letter and it can combine
Double dash = Full word and it cannot combine with other option

# Linux File system

Root folder(/)

/ is the top level directory in linux, all folder and files branch from here

/bin

Contains all the esential binaries (commands) used by all users
Exmples `ls`, `cp`, `mv`

/boot

Files needed by the system, including the linux kernel

/dev

Device files representing hardware: disk, USB, terminals
Example: /dev/sda (first hard drive)

/etc

Configuration files for the system and installed programs

Example: etc/passwd stores user accounts

/home

User home directories
example: /home/brighton store my personal files and settings

/lib

shared libraries used by programs in /bin and /sbin

/media

Mount point for removeable media (USB,external drives)

/mnt

Temporary mount point for manually mounted filesystems

/opt

Optional software packages, often third-party apps

/proc 

Virtual file system for kernel and process information

/root

Home directory of the root (admin) user, not the same as/

/sbin

System binaries for administration

/tmp

Temporary files, cleared on reboot

/usr

User programs,, libraries, and documentation

/vae

Variable data logs, mail, and databases

```
========================
🐧 Linux Command Cheat Sheet
========================

1️⃣ File & Directory Navigation
-------------------------------

pwd                 # Print current working directory
ls [options] [path] # List files in directory
cd [directory]      # Change directory
tree [directory]    # Show directory tree (install tree package)

Examples:
$ pwd
$ ls -la ~/projects
$ cd ~/linux-notes
$ tree ~
---

2️⃣ File & Directory Management
-------------------------------
mkdir [dir_name]           # Create a directory
touch [file_name]          # Create empty file
rm [file_name]             # Remove file
rm -r [folder_name]        # Remove directory recursively
cp [source] [dest]         # Copy file/folder
mv [source] [dest]         # Move or rename file/folder

Examples:
$ mkdir linux-notes
$ touch linux-notes/commands.md
$ cp aws/iam.md aws/iam-backup.md
$ mv aws/iam-backup.md projects/secure-web-app/
$ rm -r linux-notes

---

3️⃣ Viewing Files
----------------
cat [file_name]       # Display full content
less [file_name]      # Scrollable view
head [options] file   # First n lines (default 10)
tail [options] file   # Last n lines (default 10)

Examples:
$ cat linux-notes/commands.md
$ less linux-notes/commands.md
$ head -n 5 linux-notes/commands.md
$ tail -n 5 /var/log/syslog

---

4️⃣ Permissions
---------------
ls -l [directory]       # List files with permissions
chmod [mode] [file]     # Change file permissions
chown user:group [file] # Change owner/group

Examples:
$ ls -l ~/linux-notes
$ chmod 755 linux-notes/commands.md
$ chown brighton:users linux-notes/commands.md

---

5️⃣ Searching & Text Processing
--------------------------------
grep [options] pattern file    # Search pattern in file
find [path] [options]          # Find files by name/type
wc [options] file              # Count lines, words, characters

Examples:
$ grep "VPC" aws/vpc/subnets.md
$ find ~/projects -name "*.md"
$ wc -l linux-notes/commands.md

---

6️⃣ System Info & Processes
----------------------------
top                  # Show running processes
ps [options]         # Snapshot of processes
df -h                # Disk usage summary
du -sh [folder]      # Folder size summary
uname -a             # System info

Examples:
$ top
$ ps aux
$ df -h
$ du -sh ~/projects
$ uname -a

---

7️⃣ Miscellaneous
-----------------
echo "text"          # Print text to terminal
date                 # Show current date/time
clear                # Clear terminal screen
man [command]        # Show manual for a command

Examples:
$ echo "Hello World"
$ date
$ clear
$ man ls

---

💡 Tips:
```