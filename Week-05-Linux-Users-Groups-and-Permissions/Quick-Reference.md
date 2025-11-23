# Week 5 Quick Reference - Linux Commands

Quick command reference for Linux users, groups, and file management.

---

## Basic Navigation Commands

### Show Current User

```bash
whoami
```

Shows the username of the currently logged-in user.

### Show Current Directory

```bash
pwd
```

Shows the full path of the current working directory (Print Working Directory).

### List Files and Folders

```bash
ls
```

Lists files and folders in the current directory.

```bash
ls -l
```

Lists files with detailed information (permissions, owner, size, date).

```bash
ls -a
```

Lists all files including hidden files (files starting with .).

```bash
ls -la
```

Combines `-l` and `-a` flags for detailed list including hidden files.

### Change Directory

```bash
cd foldername
```

Changes into the specified folder.

```bash
cd ..
```

Goes up one directory level (parent directory).

```bash
cd
```

or

```bash
cd ~
```

Returns to home directory.

```bash
cd /
```

Changes to root directory (top level of file system).

```bash
cd -
```

Returns to the previous directory you were in.

---

## File and Folder Management Commands

### Create Folder

```bash
mkdir foldername
```

Creates a new folder (directory).

```bash
mkdir folder1 folder2 folder3
```

Creates multiple folders at once.

```bash
mkdir -p parent/child/grandchild
```

Creates nested folders (the `-p` flag creates parent directories if they don't exist).

### Create File

```bash
touch filename.txt
```

Creates an empty file or updates the timestamp of an existing file.

### Remove File

```bash
rm filename.txt
```

Deletes a file permanently (no Trash/Recycle Bin - be careful!).

```bash
rm -i filename.txt
```

Deletes with confirmation prompt (safer).

### Remove Folder

```bash
rmdir foldername
```

Removes an empty folder.

```bash
rm -r foldername
```

Removes a folder and all its contents (recursive - be very careful!).

```bash
rm -rf foldername
```

Force removes folder and contents without confirmation (extremely dangerous - use with caution!).

### Move/Rename File

```bash
mv oldname.txt newname.txt
```

Renames a file.

```bash
mv file.txt /path/to/destination/
```

Moves a file to a different location.

### Copy File

```bash
cp source.txt destination.txt
```

Copies a file.

```bash
cp -r sourcefolder destinationfolder
```

Copies a folder and all its contents (recursive).

---

## User Management Commands

### Create User

```bash
sudo useradd -m -s /bin/bash username
```

Creates a new user with:
- `-m` = creates home directory
- `-s /bin/bash` = sets Bash as the shell

```bash
sudo useradd -d /home/custompath username
```

Creates user with a specific home directory path.

```bash
sudo useradd -u 1234 username
```

Creates user with a specific User ID (UID).

### Set User Password

```bash
sudo passwd username
```

Sets or changes password for a user.

### Modify User

```bash
sudo usermod -a -G groupname username
```

Adds user to a group (secondary group):
- `-a` = append (keeps existing groups)
- `-G groupname` = add to this group
- **Always use `-a` flag!** Without it, user loses other group memberships.

```bash
sudo usermod -d /new/home/path username
```

Changes user's home directory.

```bash
sudo usermod -s /bin/zsh username
```

Changes user's default shell.

### Delete User

```bash
sudo userdel username
```

Deletes a user (keeps home directory).

```bash
sudo userdel -r username
```

Deletes user and removes home directory.

### View User Information

```bash
id username
```

Shows user's UID, GID, and all groups.

```bash
whoami
```

Shows current logged-in user.

```bash
cut -d: -f1 /etc/passwd
```

Lists all usernames on the system.

---

## Group Management Commands

### Create Group

```bash
sudo groupadd groupname
```

Creates a new group.

```bash
sudo groupadd -g 2000 groupname
```

Creates group with a specific Group ID (GID).

### Add User to Group

```bash
sudo usermod -a -G groupname username
```

Adds user to a group (secondary group).

**Important:** Always use `-a` flag to append, not replace!

### Remove User from Group

```bash
sudo gpasswd -d username groupname
```

Removes user from a group.

### Delete Group

```bash
sudo groupdel groupname
```

Deletes a group (must be empty first).

### View Group Information

```bash
getent group groupname
```

Shows group information and members.

```bash
getent group | cut -d: -f1
```

Lists all group names.

```bash
groups username
```

Shows all groups a user belongs to.

---

## File Permissions Commands

### View Permissions

```bash
ls -l filename
```

Shows detailed file information including permissions.

```bash
stat filename
```

Shows detailed file statistics including permissions.

### Change Permissions (Numeric)

```bash
chmod 755 filename
```

Sets permissions:
- 7 (4+2+1) = owner: read, write, execute
- 5 (4+1) = group: read, execute
- 5 (4+1) = others: read, execute

**Permission Numbers:**
- 4 = read (r)
- 2 = write (w)
- 1 = execute (x)
- Add them: 7 = 4+2+1 (read+write+execute)

**Common Permission Values:**
- `755` = owner: full access, others: read+execute
- `644` = owner: read+write, others: read only
- `600` = owner: read+write, others: no access
- `777` = everyone: full access (NOT recommended for security!)

### Change Permissions (Symbolic)

```bash
chmod u+x filename
```

Adds execute permission for user (owner).

```bash
chmod g+w filename
```

Adds write permission for group.

```bash
chmod o-r filename
```

Removes read permission for others.

```bash
chmod a+x filename
```

Adds execute permission for all (user, group, others).

**Symbols:**
- `u` = user (owner)
- `g` = group
- `o` = others
- `a` = all
- `+` = add permission
- `-` = remove permission
- `=` = set permission

### Change Ownership

```bash
sudo chown username filename
```

Changes file owner.

```bash
sudo chown username:groupname filename
```

Changes file owner and group.

```bash
sudo chown -R username:groupname foldername
```

Changes ownership recursively (for folders and contents).

---

## System Information Commands

### View System Information

```bash
uname -a
```

Shows system information (kernel version, etc.).

```bash
hostname
```

Shows the computer's hostname.

```bash
uptime
```

Shows how long the system has been running.

### View Disk Usage

```bash
df -h
```

Shows disk space usage (human-readable format).

```bash
du -h foldername
```

Shows disk usage of a folder (human-readable).

---

## Text File Commands

### View File Contents

```bash
cat filename.txt
```

Displays entire file contents.

```bash
less filename.txt
```

Views file page by page (press `q` to quit, space to scroll).

```bash
head filename.txt
```

Shows first 10 lines of a file.

```bash
tail filename.txt
```

Shows last 10 lines of a file.

### Edit File

```bash
nano filename.txt
```

Opens file in nano editor (user-friendly).

```bash
vim filename.txt
```

Opens file in vim editor (more advanced).

**Nano Tips:**
- `Ctrl + O` = save
- `Ctrl + X` = exit
- `Ctrl + K` = cut line
- `Ctrl + U` = paste

---

## Search Commands

### Find Files

```bash
find /path -name "filename"
```

Finds files by name.

```bash
find . -name "*.txt"
```

Finds all .txt files in current directory and subdirectories.

### Search in Files

```bash
grep "searchtext" filename.txt
```

Searches for text in a file.

```bash
grep -r "searchtext" /path
```

Searches recursively in all files.

---

## Process Management Commands

### View Running Processes

```bash
ps
```

Shows processes for current user.

```bash
ps aux
```

Shows all running processes.

```bash
top
```

Shows real-time process information (press `q` to quit).

### Kill Process

```bash
kill processid
```

Terminates a process by ID.

```bash
killall processname
```

Terminates all processes with that name.

---

## Network Commands

### Check Network Connectivity

```bash
ping google.com
```

Tests network connectivity (press `Ctrl + C` to stop).

```bash
ifconfig
```

Shows network interface configuration.

```bash
ip addr
```

Shows IP addresses (modern command).

---

## Help and Documentation

### Get Command Help

```bash
commandname --help
```

Shows help for a command.

```bash
man commandname
```

Opens manual page for a command (press `q` to quit).

```bash
info commandname
```

Shows detailed information about a command.

### Command History

```bash
history
```

Shows command history.

```bash
!number
```

Runs command from history by number.

```bash
!!
```

Runs the last command again.

---

## Useful Command Combinations

### Count Files

```bash
ls | wc -l
```

Counts number of files in current directory.

### Find Large Files

```bash
find . -type f -size +100M
```

Finds files larger than 100MB.

### Search and Replace in File

```bash
sed 's/oldtext/newtext/g' filename.txt
```

Replaces text in a file (doesn't modify original, shows output).

---

## Permission Reference

### Understanding `ls -l` Output

```
-rwxr-xr-x 1 student student 4096 Nov 23 10:00 myfile.txt
```

**Breaking it down:**
- `-` = file type (`-` = file, `d` = directory, `l` = link)
- `rwx` = owner permissions (read, write, execute)
- `r-x` = group permissions (read, execute)
- `r-x` = others permissions (read, execute)
- `1` = number of links
- `student` = owner
- `student` = group
- `4096` = size in bytes
- `Nov 23 10:00` = date and time
- `myfile.txt` = filename

### Permission Bits

| Permission | Binary | Decimal | Meaning |
|------------|--------|---------|---------|
| --- | 000 | 0 | No permissions |
| --x | 001 | 1 | Execute only |
| -w- | 010 | 2 | Write only |
| -wx | 011 | 3 | Write + Execute |
| r-- | 100 | 4 | Read only |
| r-x | 101 | 5 | Read + Execute |
| rw- | 110 | 6 | Read + Write |
| rwx | 111 | 7 | Read + Write + Execute |

---

## Common File Paths

| Path | Description |
|------|-------------|
| `/` | Root directory (top level) |
| `/home/username` | User's home directory |
| `~` | Shortcut for home directory |
| `/etc` | System configuration files |
| `/var` | Variable data files |
| `/usr` | User programs and data |
| `/bin` | Essential system binaries |
| `/sbin` | System administration binaries |
| `/tmp` | Temporary files |
| `/opt` | Optional software |

---

## Keyboard Shortcuts

| Shortcut | Action |
|----------|--------|
| `Ctrl + C` | Cancel/stop current command |
| `Ctrl + D` | Exit/logout |
| `Ctrl + L` | Clear screen |
| `Ctrl + A` | Move cursor to beginning of line |
| `Ctrl + E` | Move cursor to end of line |
| `Ctrl + U` | Clear line before cursor |
| `Ctrl + K` | Clear line after cursor |
| `Tab` | Auto-complete filename/command |
| `Tab Tab` | Show all possible completions |
| `Up Arrow` | Previous command in history |
| `Down Arrow` | Next command in history |

---

## Best Practices

1. **Always use `-a` flag with `usermod -G`** to avoid removing user from other groups
2. **Be careful with `rm`** - there's no Trash/Recycle Bin in Linux
3. **Use `sudo` only when necessary** - don't run everything as root
4. **Check commands before pressing Enter** - especially destructive ones
5. **Use `ls -l` to verify permissions** before and after changes
6. **Document your commands** - take notes for your PLR
7. **Practice regularly** - Linux commands need practice to remember
8. **Read error messages carefully** - they usually tell you what's wrong

---

## Troubleshooting

### Command Not Found

```bash
which commandname
```

Shows the path to a command (if it exists).

### Permission Denied

- Check if you need `sudo`
- Verify file permissions with `ls -l`
- Check if you own the file

### Cannot Create User

- Make sure username doesn't already exist: `id username`
- Verify you have sudo access: `sudo whoami` (should show "root")
- Check if useradd command exists: `which useradd`

### User Not in Group

- Verify with: `id username`
- Make sure you used `-a` flag: `sudo usermod -a -G groupname username`
- User may need to log out and back in for changes to take effect

---

## For Your PLR

Include these elements:

**Technical Evidence:**
- Screenshots of terminal commands and outputs
- Screenshots showing GUI vs CLI methods
- Command history showing your work
- File listings showing created files/folders

**Explanation:**
- Why Linux is important
- Differences between GUI and CLI
- How user and group management works
- What each command does

**Reflection:**
- Which method (GUI/CLI) you prefer and why
- Challenges you faced
- What you learned
- How this applies to real-world scenarios

---

**Quick access:** Keep this page open during your lab for fast command reference!

