---
title: My Linux Cheatsheet
date: 2023-12-06
description: Linux Bash shell shortcuts and commands
showHero: false
draft: false
tags: ["linux", "shell"]
---

Compilation of Linux commands and shortcuts I use often.

I've made this list for my own reference, but who knows, you might learn something from it too.

## Terminal keyboard shortcuts
- <kbd>CTRL</kbd>+<kbd>L</kbd> -> C[l]ears screen. Acts like `clear -x`, so it places the current line at the top of the screen
- <kbd>CTRL</kbd>+<kbd>E</kbd> -> Move cursor to [e]nd of line
- <kbd>CTRL</kbd>+<kbd>A</kbd> -> Move cursor to start of line
- <kbd>CTRL</kbd>+<kbd>R</kbd> -> [R]everse search in the command history. Press it again to cycle through matching commands
- <kbd>CTRL</kbd>+<kbd>W</kbd> -> Deletes [w]ord *before* the cursor
- <kbd>CTRL</kbd>+<kbd>K</kbd> -> Deletes from cursor to start of line
- <kbd>CTRL</kbd>+<kbd>X</kbd>+<kbd>E</kbd> -> Open line in default text [e]ditor. Useful for changing something in very long commands 
- <kbd>CTRL</kbd>+<kbd>Z</kbd> -> Suspends current process and moves it to background. Bring it back using `fg` or make it run in the background with `bg`
- <kbd>CTRL</kbd>+<kbd>D</kbd> at an empty prompt -> Similar to `exit`, useful for [d]isconnecting from SSH sessions 
- <kbd>CTRL</kbd>+<kbd>D</kbd> with text input -> [D]eletes character at cursor 
- <kbd>ALT</kbd>+<kbd>B</kbd> -> Move cursor [b]ack one word
- <kbd>ALT</kbd>+<kbd>F</kbd> -> Move cursor [f]orward one word

## Commands

### General

- `sudo !!` -> Runs previous command (`!!`) with `sudo`
- `echo $((RANDOM % 100 + 1))` -> Generates random number 0-100
- `echo $((2#1111))` -> Converts binary (1111) to decimal
- `echo $((16#1a))` -> Converts hexadecimal (1a) to decimal
- `tr -dc '[:alnum:]' < /dev/urandom | head -c 32` -> Generates random alphanumeric password 
- `time [command]` -> Shows time it took to execute a command
-  `[command] | tee output.txt` -> Redirect output to terminal and file at the same time
- `hostnamectl` -> Displays hostname and other goodies

### Processes

- `systemctl list-units --type=service` -> Lists all active services
- `systemctl edit [service]` -> Edit configuration of a service
- `systemctl --failed` -> Lists services that failed to start
- `ps aux --sort=-%cpu | head` -> Display top CPU-consuming processes.
- `w` -> Displays users logged in and what they are doing

### Networking

- `ip a` -> Show network interfaces info
- `ip link set [interface] up|down` -> Set interface up or down
- `ip addr add|del ip/mask dev [interface]` -> Add or delete IP address to interface
- `curl ifconfig.me` -> Retrieve public IP address. Use `curl ifconfig.me/all` for more
- `ss -tunap` -> Lists all TCP and UDP sockets with their state of connection, PID that owns it and local/remote addresses
- `ss -tunalp` -> Lists all TCP and UDP sockets that are listening, along with PID and addresses
- `nc -l -p [port]` -> Listen on port
- `ip route show` -> Shows kernel's routing table
- `nslookup example.com` and `dig example.com` -> DNS lookup utilities

### Working with files/logs

- `grep -r "pattern"` -> Searches for a pattern recursively in all files
- `tail -f [path]` -> Outputs logs in real time. You can further `grep` the output to get exactly what you're looking for
- `dd if=/dev/zero of=file bs=1M count=100` -> Creates 100MB file filled with zeros
- `rsync --dry-run` [source] [destination] -> Simulates rsync operation without actually doing anything

### Disks
- `lsblk` -> List block devices (disks)
- `df -h` -> See disk space usage in a human readable format
- `du -sh *` -> See disk space used by each file and directory in current location 
- `parted /dev/sdX` -> Disk partitioning tool
- `findmnt` -> Displays info about mounted file systems
- `sudo mkfs.ext4 /dev/sdX` -> Creates ext4 filesystem. Replace `ext4` with filesystem of choice
#### LVM
- `pvdisplay` -> Display info about physical volumes
- `vgdisplay` -> Display info about volume groups
- `lvdisplay` -> Dsiplay info about logical volumes
- `sudo lvcreate -L 10G -n lv_name vg_name` -> Create 10GB logical volume
- `sudo lvextend -L +10G /dev/vg_name/lv_name` -> Extend logical volume by 5GB
- `sudo lvreduce -L -3G /dev/vg_name/lv_name` -> Shrink logical volume by 3GB

###  Archives and compression

Add `v` to any of these to make them verbose

- `tar cf output.tar file1 file2` -> [c]reate archive and write it to [f]ile
- `tar czf output.tar.gz file1 file2` -> [c]reate g[z]ipped compressed archive and write it to [f]ile
- `tar xf source.tar` -> Extract archive [f]ile into current directory
- `tar tf source.tar` -> Lis[t] contents of tar [f]ile
- `zip -r archive.zip file1 directory1` -> Creates archive with specified files and directories 
- `zip -r -[0-9] archive.zip file1 directory1` -> Creates archive with specific compression level (0 is lowest, 9 is highest)
- `zip -r --encrypt archive.zip file1 directory1` -> Creates encrypted archive with password
- `unzip archive.zip` -> Extracts from archive into current directory
- `unzip -l archive.zip` -> Lists contents of an archive. Does not extract anything


If you want to suggest any commands, put them in the comments, I would love to see them.


{{< chat linux-cheatsheet >}}
