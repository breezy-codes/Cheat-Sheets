# Linux Commands Cheat Sheet

## File and Directory Management

### Navigation

- Change directory:  
   `cd /path/to/directory`
- Go to the home directory:  
   `cd ~`
- Go to the previous directory:  
   `cd -`
- List files and directories:  
   `ls`
- List detailed file info:  
   `ls -l`
- List hidden files:  
   `ls -a`

### File Operations

- Copy files:  
   `cp source destination`
- Copy directories:  
   `cp -r source_dir destination_dir`
- Move or rename files:  
   `mv source destination`
- Delete files:  
   `rm file.txt`
- Delete directories:  
   `rm -r directory_name`
- Create a new file:  
   `touch file.txt`
- Create a new directory:  
   `mkdir directory_name`
- Remove an empty directory:  
   `rmdir directory_name`

---

## File Viewing and Editing

### Viewing Files

- Display file content:  
   `cat file.txt`
- View file content one page at a time:  
   `less file.txt`
- Display the first 10 lines of a file:  
   `head file.txt`
- Display the last 10 lines of a file:  
   `tail file.txt`
- Follow a file in real-time:  
   `tail -f file.txt`

### Editing Files

- Edit files using `nano`:  
   `nano file.txt`
- Edit files using `vim`:  
   `vim file.txt`

---

## File Permissions and Ownership

### Changing Permissions

- Change file permissions (e.g., `rwx`):  
   `chmod 755 file.txt`
- Change directory permissions recursively:  
   `chmod -R 755 directory_name`

### Changing Ownership

- Change file owner:  
   `chown user file.txt`
- Change file owner and group:  
   `chown user:group file.txt`
- Change ownership recursively:  
   `chown -R user:group directory_name`

---

## Searching and Finding Files

### File Search

- Search for a file by name:  
   `find /path -name "filename"`
- Search for files by extension:  
   `find /path -name "*.txt"`

### Content Search

- Search for text in a file:  
   `grep 'pattern' file.txt`
- Search recursively in a directory:  
   `grep -r 'pattern' /path`

---

## Disk and System Information

### Disk Usage

- Check disk space usage:  
   `df -h`
- Check directory or file size:  
   `du -sh /path`

### System Information

- Display system information:  
   `uname -a`
- Show current logged-in users:  
   `who`
- Display memory usage:  
   `free -h`
- Show running processes:  
   `top`
- Display detailed process list:  
   `ps aux`

---

## Networking

### Network Configuration

- Display IP address:  
   `ip addr`
- Test network connectivity:  
   `ping example.com`
- Display open network ports:  
   `netstat -tuln`

### File Transfers

- Copy files between systems:  
   `scp file.txt user@remote:/path`
- Download files using `wget`:  
   `wget http://example.com/file.zip`

---

## Process Management

### Process Operations

- Show current running processes:  
   `ps aux`
- Kill a process by PID:  
   `kill PID`
- Kill a process by name:  
   `pkill process_name`

### Background and Foreground

- Run a command in the background:  
   `command &`
- List background jobs:  
   `jobs`
- Bring a background job to the foreground:  
   `fg %job_number`

---

## User Management

### User and Group Operations

- Add a new user:  
   `sudo useradd username`
- Change a user's password:  
   `sudo passwd username`
- Add a user to a group:  
   `sudo usermod -aG groupname username`

### Switching Users

- Switch to another user:  
   `su - username`
- Execute a command as another user:  
   `sudo command`

---

## Archiving and Compression

### Creating Archives

- Create a `.tar` archive:  
   `tar -cvf archive.tar file_or_directory`
- Create a compressed `.tar.gz` archive:  
   `tar -czvf archive.tar.gz file_or_directory`

### Extracting Archives

- Extract a `.tar` archive:  
   `tar -xvf archive.tar`
- Extract a `.tar.gz` archive:  
   `tar -xzvf archive.tar.gz`

---

## Package Management

### Debian/Ubuntu (APT)

- Update package list:  
   `sudo apt update`
- Upgrade all packages:  
   `sudo apt upgrade`
- Install a package:  
   `sudo apt install package_name`
- Remove a package:  
   `sudo apt remove package_name`

### Red Hat/CentOS (YUM/DNF)

- Install a package:  
   `sudo yum install package_name`  
   `sudo dnf install package_name`
- Remove a package:  
   `sudo yum remove package_name`  
   `sudo dnf remove package_name`

### Arch Linux (Pacman)

- Update package list:  
   `sudo pacman -Sy`
- Upgrade all packages:
- Install a package:  
   `sudo pacman -S package_name`
- Remove a package:
- `sudo pacman -R package_name`
- Search for a package:  
   `pacman -Ss search_term`

### Arch Linux (yay)

- Install a package:  
   `yay -S package_name`
- Remove a package:
   `yay -R package_name`
- Search for a package:  
   `yay -Ss search_term`

---

## Shell Scripting

### Variables and Scripts

- Assign a variable:  
   `variable_name="value"`
- Print a variable:  
   `echo $variable_name`
- Run a shell script:  
   `bash script.sh`

### Loops and Conditions

- Example `for` loop:

  ```bash
  for i in {1..5}; do
      echo $i
  done
  ```

- Example `if` statement:

  ```bash
  if [ condition ]; then
      echo "Condition met"
  fi
  ```

---

## Miscellaneous

### History and Aliases

- Show command history:  
   `history`
- Create a command alias:  
   `alias ll='ls -la'`

### Permissions and Ownership

- Display current working directory:  
   `pwd`
- Change the hostname:  
   `sudo hostname new_hostname`
