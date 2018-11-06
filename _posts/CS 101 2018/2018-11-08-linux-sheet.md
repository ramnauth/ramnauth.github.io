---
# Posts need to have the `post` layout
layout: post

# The title of your post
title: Bash/Linux Commands - Reference Sheet

# (Optional) Write a short (~150 characters) description of each blog post.
# This description is used to preview the page on search engines, social media, etc.
description: >
	

# (Optional) Link to an image that represents your blog post.
# The aspect ratio should be ~16:9.
image: /assets/img/default.jpg

# You can hide the description and/or image from the output
# (only visible to search engines) by setting:
# hide_description: true
# hide_image: true

# (Optional) Each post can have zero or more categories, and zero or more tags.
# The difference is that categories will be part of the URL, while tags will not.
# E.g. the URL of this post is <site.baseurl>/hydejack/2017/11/23/example-content/
categories: [CS 101]
tags: [Programming Basics]
# If you want a category or tag to have its own page,
# check out `_featured_categories` and `_featured_tags` respectively.
---
Bash is a Unix shell and command language. It has been distributed widely as the default login shell for most Linux distributions and Apple's macOS/OS X. Bash typically runs in a text window where you can type commands, telling the computer what to do. 

Bash was written for the **GNU Project** as a **free software** replacement for the [Bourne shell](https://en.wikipedia.org/wiki/Bourne_shell). The name "Bash" is an acronym for *Bourne-again shell*, a pun on the word Bourne and "born again".

## System Information
```shell
uname -a		# Display Linux system information
uname -r		# Display kernel release information
uptime			# Show how long the system has been running + load
hostname		# Show system host name
hostname -I		# Display the IP addresses of the host
last reboot		# Show system reboot history
date			# Show the current date and time
w				# Display who is online
whoami			# Who you are logged in as
```

## Hardware Information
```shell
cat /proc/cpuinfo	# Display CPU information
cat /proc/meminfo	# Display memory information
free				# Display free and used memory 
free -h				# -h for human readable
free -m				# -m for MB
free -g				# -g for GB 
```

## Performance Monitoring & Stats
```shell
top				# Display and manage the top processes
vmstat 1		# Display virtual memory statistics
free -h			# Display free and used memory ( -h for human readable, -m for MB, -g for GB.)
watch df -h		# Execute "df -h", showing periodic updates
```

## User Information & Management
```shell
id				# Display the user and group ids of your current user.
last			# Display the last users who have logged onto the system.
w				# Show who is logged in and what they are doing.
```

## File & Directory Commands
```shell
ls -al				# List all files in a long listing (detailed) format
pwd					# Display the present working directory

touch file			# Create a file
mkdir directory		# Create a directory

rm file				# Remove (delete) file
rm -r directory		# Remove the directory and its contents recursively

cp file1 file2		# Copy file1 to file2
cp -r source_directory destination		# Copy source_directory recursively to destination. If destination exists, copy source_directory into destination, otherwise create destination with the contents of source_directory.

mv file1 file2		# Rename or move file1 to file2. If file2 is an existing directory, move file1 into directory file2

cat file			# View the contents of file
cat > file			# Replace the contents of file

head file			# Display the first 10 lines of file
tail file			# Display the last 10 lines of file
tail -f file		# Display the last 10 lines of file and "follow" the file as it grows.
```

### The vi Editor
**vi** is a **text editor** that was created for the Unix operating system. 

```shell
vi file 	# Open file in the vi editor
```

Here are some file management commands in vi.

```shell
:w name 	# Write edit buffer to file name
:wq		# Write to file and quit
:q!		# Quit without saving changes
ZZ		# Same as :wq
:sh		# Execute shell commands(<ctrl> d)
:i		# Turn on edit/insert mode
```

## Process Management
```shell
ps			# Display your currently running processes
ps -ef		# Display all the currently running processes with more information
top			# Display and manage the top processes
kill pid	# Kill process with process ID of pid
```

## File Permissions
![File Permissions](https://www.linuxtrainingacademy.com/wp-content/uploads/2017/02/linux-permissions-chart.png)

```
        PERMISSION      EXAMPLE

         U   G   W
        rwx rwx rwx     chmod 777 filename
        rwx rwx r-x     chmod 775 filename
        rwx r-x r-x     chmod 755 filename
        rw- rw- r--     chmod 664 filename
        rw- r-- r--     chmod 644 filename
		
		LEGEND
        U = User
        G = Group
        W = World

        r = Read
        w = write
        x = execute
        - = no access
```

## Networking
```shell
ping host						# Send ICMP echo request to host
host domain						# Display DNS ip address for domain
hostname -i						# Display the network address of the host name.
hostname -I						# Display all local ip addresses
wget http://domain.com/file		# Download http://domain.com/file
```

## Searching
```shell
grep pattern file					# Search for pattern in file
grep -r pattern directory			# Search recursively for pattern in directory
locate name							# Find files and directories by name
find /home/john -name 'prefix*'		# Find files in /home/john that start with "prefix".
find /home -size +100M				# Find files larger than 100MB in /home
```

## Disk Usage
```shell
df -h		# Show free and used space on mounted filesystems
df -i		# Show free and used inodes on mounted filesystems
du -ah		# Display disk usage for all files and directories in human readable format
du -sh		# Display total disk usage off the current directory
```

## Directory Navigation
```shell
cd ..		# To go up one level of the directory tree.  (Change into the parent directory.)
cd			# Go to the $HOME directory
cd /etc		# Change to the /etc directory
```