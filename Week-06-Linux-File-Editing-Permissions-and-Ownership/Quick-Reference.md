# Week 6 Quick Reference - File Editing, Moving, Copying, and Permissions

Quick command reference for Linux file operations and permissions.

---

## File Editing Commands

### Open File in Nano Editor

```bash
nano filename.txt
```

Opens file in nano editor (user-friendly).

**Nano Keyboard Shortcuts:**
- `Ctrl + O` = Save (Write Out)
- `Ctrl + X` = Exit
- `Ctrl + K` = Cut line
- `Ctrl + U` = Paste
- `Ctrl + W` = Search
- `Ctrl + G` = Get Help

### Open File in Vim Editor

```bash
vim filename.txt
```

Opens file in vim editor (advanced).

**Vim Basics:**
- Press `i` to enter insert mode (start editing)
- Press `Esc` to exit insert mode
- Type `:wq` and press Enter to save and quit
- Type `:q!` and press Enter to quit without saving

### View File Contents

```bash
cat filename.txt
```

Displays entire file contents.

```bash
less filename.txt
```

Views file page by page (press `q` to quit, space to scroll, arrow keys to navigate).

```bash
head filename.txt
```

Shows first 10 lines of a file.

```bash
head -n 20 filename.txt
```

Shows first 20 lines.

```bash
tail filename.txt
```

Shows last 10 lines of a file.

```bash
tail -n 20 filename.txt
```

Shows last 20 lines.

```bash
tail -f filename.txt
```

Shows last lines and follows file (updates as file changes - press `Ctrl + C` to stop).

---

## Moving Files Commands

### Move File

```bash
mv source.txt destination.txt
```

Moves or renames a file.

```bash
mv file.txt /path/to/destination/
```

Moves file to a different location.

```bash
mv file.txt ../Documents/
```

Moves file to parent directory's Documents folder.

```bash
mv oldname.txt newname.txt
```

Renames a file (mv can rename or move).

### Move Multiple Files

```bash
mv file1.txt file2.txt file3.txt /destination/
```

Moves multiple files to destination.

### Move Folder

```bash
mv foldername /path/to/destination/
```

Moves entire folder and contents.

---

## Copying Files Commands

### Copy File

```bash
cp source.txt destination.txt
```

Copies a file to a new location or name.

```bash
cp file.txt /path/to/destination/
```

Copies file to a different location.

```bash
cp file.txt file_backup.txt
```

Creates a copy with a new name in the same directory.

### Copy Folder

```bash
cp -r sourcefolder destinationfolder
```

Copies folder and all contents (recursive).

```bash
cp -r folder1 folder2 folder3 /destination/
```

Copies multiple folders.

### Copy with Preserve Attributes

```bash
cp -p source.txt destination.txt
```

Copies file preserving timestamps and permissions.

```bash
cp -a sourcefolder destinationfolder
```

Copies folder preserving all attributes (archive mode).

---

## File Permissions Commands

### View Permissions

```bash
ls -l filename
```

Shows detailed file information including permissions.

```bash
ls -ld foldername
```

Shows directory permissions (the `d` flag shows directory info, not contents).

```bash
stat filename
```

Shows detailed file statistics including permissions.

### Change Permissions (Symbolic Method)

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

```bash
chmod u+w,g+r,o-r filename
```

Multiple changes: user write, group read, others no read.

**Symbols:**
- `u` = user (owner)
- `g` = group
- `o` = others
- `a` = all
- `+` = add permission
- `-` = remove permission
- `=` = set exact permission

### Change Permissions (Numeric Method)

```bash
chmod 755 filename
```

Sets permissions:
- 7 (owner) = read + write + execute
- 5 (group) = read + execute
- 5 (others) = read + execute

```bash
chmod 644 filename
```

Sets permissions:
- 6 (owner) = read + write
- 4 (group) = read only
- 4 (others) = read only

```bash
chmod 600 filename
```

Sets permissions:
- 6 (owner) = read + write
- 0 (group) = no access
- 0 (others) = no access

```bash
chmod 777 filename
```

Sets full permissions for everyone (NOT recommended - security risk!).

**Permission Numbers:**
- 4 = read (r)
- 2 = write (w)
- 1 = execute (x)
- Add them: 7 = 4+2+1 (read+write+execute)

**Common Values:**
- `755` = owner: full, group/others: read+execute (programs)
- `644` = owner: read+write, group/others: read (files)
- `600` = owner: read+write, others: no access (private)
- `777` = everyone: full access (dangerous!)

### Change Permissions Recursively

```bash
chmod -R 755 foldername
```

Changes permissions for folder and all contents recursively.

```bash
chmod -R u+w foldername
```

Adds write permission for owner on folder and all contents.

---

## File Ownership Commands

### Change File Owner

```bash
sudo chown username filename
```

Changes file owner (requires sudo).

```bash
sudo chown root filename
```

Changes owner to root user.

### Change Owner and Group

```bash
sudo chown username:groupname filename
```

Changes both owner and group.

```bash
sudo chown student:student filename
```

Changes owner and group to student.

### Change Ownership Recursively

```bash
sudo chown -R username:groupname foldername
```

Changes ownership for folder and all contents recursively.

### Change Group Only

```bash
sudo chgrp groupname filename
```

Changes group ownership only.

```bash
sudo chgrp -R groupname foldername
```

Changes group recursively.

---

## Understanding Permissions

### Reading `ls -l` Output

```
-rwxr-xr-x 1 student student 4096 Nov 23 15:30 myfile.txt
```

**Breaking it down:**
- `-` = file type (`-` = file, `d` = directory, `l` = link)
- `rwx` = owner permissions (read, write, execute)
- `r-x` = group permissions (read, execute)
- `r-x` = others permissions (read, execute)
- `1` = number of hard links
- `student` = owner
- `student` = group
- `4096` = size in bytes
- `Nov 23 15:30` = date and time
- `myfile.txt` = filename

### Permission Bits Reference

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

### Permission Meanings

**Read (r / 4):**
- For files: Can view file contents
- For directories: Can list directory contents

**Write (w / 2):**
- For files: Can modify or delete file
- For directories: Can create/delete files in directory

**Execute (x / 1):**
- For files: Can run file as a program/script
- For directories: Can enter (cd into) the directory

---

## Common Permission Scenarios

### Make File Private (Owner Only)

```bash
chmod 600 filename
```

Result: `-rw-------` (only owner can read and write)

### Make File Readable by All, Writable by Owner

```bash
chmod 644 filename
```

Result: `-rw-r--r--` (owner: read+write, others: read only)

### Make Script Executable

```bash
chmod +x script.sh
```

Adds execute permission for all.

```bash
chmod 755 script.sh
```

Owner: full access, others: read+execute.

### Make Directory Accessible

```bash
chmod 755 foldername
```

Allows everyone to enter and list contents, only owner can modify.

```bash
chmod 700 foldername
```

Only owner can access (private directory).

---

## File Operations Quick Reference

### Create and Edit

```bash
touch newfile.txt          # Create empty file
nano newfile.txt           # Create and edit in nano
vim newfile.txt            # Create and edit in vim
```

### View Contents

```bash
cat file.txt               # View entire file
less file.txt              # View page by page
head file.txt              # View first 10 lines
tail file.txt              # View last 10 lines
```

### Move and Copy

```bash
mv old.txt new.txt         # Rename file
mv file.txt /path/         # Move file
cp file.txt backup.txt     # Copy file
cp -r folder1 folder2     # Copy folder
```

### Permissions

```bash
ls -l                      # View permissions
chmod 755 file.txt         # Set permissions (numeric)
chmod u+x file.txt         # Add permission (symbolic)
chown user:group file.txt  # Change ownership
```

---

## GUI Methods Quick Reference

### Opening Files

1. **File Manager:**
   - Click Files icon
   - Navigate to file
   - Double-click to open

2. **Text Editor:**
   - Press Super key
   - Search "Text Editor"
   - Click to open
   - File → Open to open file

### Moving Files (GUI)

1. Open two File Manager windows
2. Navigate to source in first window
3. Navigate to destination in second window
4. Drag file from first to second window

### Copying Files (GUI)

1. Right-click file → Copy
2. Navigate to destination
3. Right-click empty area → Paste

---

## Troubleshooting Commands

### Check Current Permissions

```bash
ls -l filename
```

Shows current permissions and ownership.

### Check Directory Permissions

```bash
ls -ld foldername
```

Shows directory permissions (important for deleting files).

### Check Who You Are

```bash
whoami
```

Shows current username.

```bash
id
```

Shows current user's UID, GID, and groups.

### Check File Owner

```bash
stat filename
```

Shows detailed file information including owner.

---

## Common Issues and Solutions

### Permission Denied When Editing

```bash
# Check permissions
ls -l filename

# Add write permission for owner
chmod u+w filename

# Or use sudo if you're not the owner
sudo chmod u+w filename
```

### Cannot Execute Script

```bash
# Check permissions
ls -l script.sh

# Add execute permission
chmod +x script.sh

# Try running again
./script.sh
```

### Cannot Delete File

```bash
# Check directory permissions (not file permissions!)
ls -ld foldername

# You need write permission on the directory to delete files
chmod u+w foldername
```

### Cannot Access Directory

```bash
# Check directory permissions
ls -ld foldername

# Add execute permission (needed to enter directory)
chmod +x foldername
```

### File Owned by Root

```bash
# Change ownership back to your user
sudo chown $USER:$USER filename

# Or change to specific user
sudo chown student:student filename
```

---

## Best Practices

1. **Use appropriate permissions:**
   - Files: `644` (owner read+write, others read)
   - Scripts: `755` (owner full, others read+execute)
   - Private files: `600` (owner only)

2. **Never use `777` permissions:**
   - Security risk - gives everyone full access
   - Use `755` or `644` instead

3. **Understand directory permissions:**
   - Need execute permission to enter directory
   - Need write permission to create/delete files in directory

4. **Use symbolic method for learning:**
   - Easier to understand: `chmod u+x file`
   - Use numeric method for scripts: `chmod 755 file`

5. **Always check before changing:**
   - `ls -l` to see current permissions
   - Understand what you're changing

6. **Be careful with recursive changes:**
   - `chmod -R` affects all files in folder
   - Double-check the path before running

---

## Permission Calculation Cheat Sheet

### Quick Calculation

| Desired | Read? | Write? | Execute? | Number |
|---------|-------|--------|----------|--------|
| No access | No | No | No | 0 |
| Execute only | No | No | Yes | 1 |
| Write only | No | Yes | No | 2 |
| Write + Execute | No | Yes | Yes | 3 |
| Read only | Yes | No | No | 4 |
| Read + Execute | Yes | No | Yes | 5 |
| Read + Write | Yes | Yes | No | 6 |
| Full access | Yes | Yes | Yes | 7 |

### Common Combinations

- `755` = Owner: full (7), Group: read+execute (5), Others: read+execute (5)
- `644` = Owner: read+write (6), Group: read (4), Others: read (4)
- `600` = Owner: read+write (6), Group: none (0), Others: none (0)
- `750` = Owner: full (7), Group: read+execute (5), Others: none (0)

---

## For Your PLR

Include these elements:

**Technical Evidence:**
- Screenshots of `ls -l` showing permissions
- Screenshots of `chmod` commands and results
- Screenshots of `chown` commands
- Before/after permission comparisons

**Explanation:**
- How file permissions work
- Difference between read, write, execute
- Why permissions are important for security
- When to use symbolic vs numeric notation

**Reflection:**
- Challenges with permissions
- How you troubleshooted issues
- What you learned about Linux security
- Real-world applications

---

**Quick access:** Keep this page open during your lab for fast command reference!

