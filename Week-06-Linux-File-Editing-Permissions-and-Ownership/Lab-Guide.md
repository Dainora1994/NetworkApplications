# Week 6 Lab Guide: Linux File Editing, Permissions, and Ownership

Complete guide showing both GUI (Graphical User Interface) and CLI (Command Line Interface) methods.

---

## Lab Overview

### What is Week 6 About:
**Editing Files, Moving/Copying Files, and Managing File Permissions and Ownership in Linux**

### PC Requirements:
- **Ubuntu Linux** (Virtual Machine, lab PC, or LOD platform)
- Terminal/Shell access
- Text editor (nano, vim, or gedit)
- Basic familiarity with CLI commands from Week 5
- Administrator/sudo privileges

### What You'll Do:
- **Activity 1:** Edit files using text editors (GUI and Terminal methods)
- **Activity 2:** Move and copy files between directories (GUI and Terminal methods)
- **Activity 3:** Understand and manage file permissions and ownership

---

## Important Terms

| Term | Definition | Simple Explanation |
|------|------------|-------------------|
| Text Editor | Program for creating and editing text files | Like Notepad in Windows, but for Linux |
| Nano | Simple, beginner-friendly text editor | Easy to use, shows commands at bottom |
| Vim | Advanced text editor with many features | More powerful but harder to learn |
| Gedit | Graphical text editor (GUI) | Like Notepad with a graphical interface |
| Move (mv) | Command to move or rename files | Changes file location or name |
| Copy (cp) | Command to duplicate files | Creates a copy of a file |
| Ownership | Who owns a file (user and group) | Like property ownership - who "owns" the file |
| chown | Command to change file ownership | Changes who owns a file |
| chmod | Command to change file permissions | Changes who can read/write/execute a file |
| Read Permission | Permission to view file contents | Can see what's in the file |
| Write Permission | Permission to modify file contents | Can change or delete the file |
| Execute Permission | Permission to run file as a program | Can execute/run the file |
| Symbolic Notation | Using letters (r, w, x) for permissions | Easy to read: r=read, w=write, x=execute |
| Numeric Notation | Using numbers (0-7) for permissions | Compact: 7=rwx, 5=r-x, 4=r-- |

---

## Background Knowledge: File Operations

**What we're learning:**
- How to edit files in Linux (both GUI and command line)
- How to move and copy files between locations
- How file permissions work and why they're important
- How to change file ownership

**Why this matters:**
- File editing is essential for configuration and scripting
- Moving/copying files is a daily task in system administration
- Understanding permissions is critical for security
- Ownership controls who can access and modify files

---

## SETUP: PREPARING FOR WEEK 6

**What we're doing:** We need to set up our Ubuntu environment and create some practice files.

1. **Start your Ubuntu system**
   - Open your Ubuntu VM, lab PC, or LOD platform
   - Log in with your credentials

2. **Open Terminal**
   - Press **Ctrl + Alt + T**
   - *Terminal window opens*

3. **Create a practice folder**
   - Type: `mkdir -p ~/Documents/Week6Lab`
   - Press Enter
   - *This creates a folder for our Week 6 practice*

4. **Navigate to the folder**
   - Type: `cd ~/Documents/Week6Lab`
   - Press Enter
   - *You're now in the Week6Lab folder*

5. **Create a practice file**
   - Type: `touch Practice.txt`
   - Press Enter
   - *This creates an empty file we'll use for practice*

**What you should see:**
```
$ mkdir -p ~/Documents/Week6Lab
$ cd ~/Documents/Week6Lab
$ touch Practice.txt
$ ls
Practice.txt
$
```

---

## ACTIVITY 1: EDITING FILES WITH TEXT EDITORS

**Do on:** Ubuntu Linux system

**What we're doing:** We're learning to edit text files using both graphical editors (GUI) and command-line editors (CLI). This is essential for configuration files, scripts, and documentation.

**Goal:** Learn to edit files using GUI and Terminal text editors.

**Time:** 30 minutes

---

## TASK 1: EDIT FILES USING GUI (File Manager)

**What this does:** We're editing a file using the graphical interface, which is similar to editing files in Windows.

### GUI METHOD (File Manager)

1. **Open File Manager**
   - Click the **Files** icon in the launcher (left side of screen)
   - OR press **Super key + N** (Super key is usually the Windows key)
   - *A File Manager window opens*

2. **Navigate to your file**
   - *In File Manager, you will see folders in the left pane*
   - *Click on **Documents** in the left pane*
   - *You will see the contents of Documents folder*
   - *Double-click **Week6Lab** folder*
   - *You will see **Practice.txt** file*

3. **Open the file**
   - *In File Manager, you will see **Practice.txt***
   - *Double-click on **Practice.txt***
   - *The file opens in the default text editor (usually Text Editor/Gedit)*
   - *You will see a text editor window with the file open*

4. **Edit the file**
   - *In the text editor window, you can type text*
   - *Type some text, for example: "This is my practice file for Week 6"*
   - *You will see the text appear as you type*

5. **Save the file**
   - *In the text editor, click **File** in the menu bar*
   - *You will see a dropdown menu*
   - *Click **Save** (or press **Ctrl + S**)*
   - *The file is saved*

6. **Close the editor**
   - *Click the **X** button in the top-right corner*
   - *OR click **File** → **Close***
   - *The editor window closes*

**What you should see:**
- File Manager showing your file
- Text editor opening when you double-click the file
- Your text appearing in the editor
- File saving successfully

---

## TASK 2: FIND TEXT EDITOR FROM GUI

**What this does:** We're learning to open the Text Editor application directly from the GUI, which is useful when you want to create a new file or open the editor first.

### GUI METHOD

1. **Open Show Applications**
   - *Look at the bottom-left corner of your screen*
   - *You will see a grid icon (9 dots in a square)*
   - *Click it*
   - *OR press **Super key** (Windows key)*
   - *The Applications menu opens*

2. **Search for Text Editor**
   - *In the Applications menu, you will see a search bar at the top*
   - *Type **"Text Editor"** in the search bar*
   - *You will see "Text Editor" appear in the results*
   - *It may also show as "Gedit" or "Text Editor"*

3. **Open Text Editor**
   - *Click on **Text Editor** (or Gedit) icon*
   - *A Text Editor window opens*
   - *You will see an empty editor window*

4. **Create or open a file**
   - *In Text Editor, click **File** → **Open***
   - *A file browser window opens*
   - *Navigate to **Documents/Week6Lab***
   - *Select **Practice.txt** and click **Open***
   - *The file opens in the editor*

**What you should see:**
- Applications menu opening
- Text Editor appearing in search results
- Text Editor window opening
- Your file opening in the editor

---

## TASK 3: EDIT FILES USING NANO (Terminal)

**What this does:** We're learning to edit files using nano, a simple command-line text editor. This is very useful when working remotely or when you prefer the command line.

### CLI METHOD (Nano Editor)

1. **Open Terminal**
   - Press **Ctrl + Alt + T**
   - *Terminal window opens*

2. **Navigate to your folder**
   - Type: `cd ~/Documents/Week6Lab`
   - Press Enter
   - *You're in the Week6Lab folder*

3. **Open file in nano**
   - Type: `nano Practice.txt`
   - Press Enter
   - *Nano editor opens with your file*

**What you should see:**
- Terminal showing nano editor
- Your file contents (if any) displayed
- At the bottom, you will see helpful commands:
  - `^O Write Out` (means Ctrl+O to save)
  - `^X Exit` (means Ctrl+X to exit)
  - `^` means the Ctrl key

4. **Edit the file**
   - *In nano, you can type text directly*
   - *Type some text, for example: "Learning to use nano editor"*
   - *You will see the text appear as you type*
   - *Use arrow keys to move the cursor*

5. **Save the file**
   - Press **Ctrl + O** (hold Ctrl, press O)
   - *At the bottom, you will see: "File Name to Write: Practice.txt"*
   - Press **Enter** to confirm
   - *You will see a message: "[ Wrote 1 line ]" or similar*
   - *The file is saved*

6. **Exit nano**
   - Press **Ctrl + X**
   - *Nano closes and you return to the terminal*
   - *You will see your normal terminal prompt*

**What you should see:**
```
$ nano Practice.txt

[Your file content appears here]
Learning to use nano editor

^G Get Help  ^O Write Out  ^X Exit
```

**Nano Keyboard Shortcuts:**
- **Ctrl + O** = Save (Write Out)
- **Ctrl + X** = Exit
- **Ctrl + K** = Cut line
- **Ctrl + U** = Paste
- **Ctrl + W** = Search
- **Ctrl + G** = Get Help

---

## TASK 4: READ FILE CONTENTS (Terminal)

**What this does:** We're learning to view file contents in the terminal without opening an editor. This is useful for quickly checking file contents.

### CLI METHOD

1. **View entire file**
   - Type: `cat Practice.txt`
   - Press Enter
   - *The entire file contents are displayed*

**What you should see:**
```
$ cat Practice.txt
Learning to use nano editor
This is my practice file for Week 6
$
```

2. **View file page by page**
   - Type: `less Practice.txt`
   - Press Enter
   - *File opens in less viewer*
   - *You can scroll with arrow keys*
   - *Press **q** to quit*

3. **View first few lines**
   - Type: `head Practice.txt`
   - Press Enter
   - *Shows first 10 lines of the file*

4. **View last few lines**
   - Type: `tail Practice.txt`
   - Press Enter
   - *Shows last 10 lines of the file*

---

## ACTIVITY 2: MOVING AND COPYING FILES

**Do on:** Ubuntu Linux system

**What we're doing:** We're learning to move and copy files between directories. Moving changes the file location, while copying creates a duplicate.

**Goal:** Learn to move and copy files using both GUI and Terminal methods.

**Time:** 20 minutes

---

## TASK 5: MOVE FILE USING GUI

**What this does:** We're moving a file from one folder to another using the graphical interface, like dragging and dropping in Windows.

### GUI METHOD (File Manager)

1. **Open two File Manager windows**
   - Click the **Files** icon to open File Manager
   - *One File Manager window opens*
   - Click the **Files** icon again (or press **Super + N**)
   - *A second File Manager window opens*
   - *You now have two windows open*

2. **Set up the windows**
   - *In the first window, navigate to **Documents/Week6Lab***
   - *You will see **Practice.txt** in this window*
   - *In the second window, navigate to **Downloads***
   - *This window should be empty or show other files*

3. **Move the file**
   - *In the first window (Documents/Week6Lab), you will see **Practice.txt***
   - *Click and hold on **Practice.txt***
   - *Drag it to the second window (Downloads)*
   - *Release the mouse button*
   - *The file moves to Downloads*

**What you should see:**
- Practice.txt disappears from Documents/Week6Lab
- Practice.txt appears in Downloads
- The file has been moved (not copied)

---

## TASK 6: MOVE FILE USING TERMINAL

**What this does:** We're moving a file using the `mv` command. This is faster and more precise than using the GUI.

### CLI METHOD (mv command)

1. **Open Terminal**
   - Press **Ctrl + Alt + T**
   - *Terminal window opens*

2. **Navigate to Downloads**
   - Type: `cd ~/Downloads`
   - Press Enter
   - *You're now in Downloads folder*

3. **Move file back to Documents/Week6Lab**
   - Type: `mv Practice.txt ~/Documents/Week6Lab/`
   - Press Enter
   - *The file is moved immediately*
   - *No message appears - if there's no error, it worked!*

**What this command does:**
- `mv` = move command
- `Practice.txt` = source file (current location)
- `~/Documents/Week6Lab/` = destination folder

4. **Verify the file was moved**
   - Type: `ls ~/Documents/Week6Lab/`
   - Press Enter
   - *You will see Practice.txt listed*

5. **Check Downloads is empty**
   - Type: `ls`
   - Press Enter
   - *Practice.txt should not be in Downloads anymore*

**What you should see:**
```
$ cd ~/Downloads
$ mv Practice.txt ~/Documents/Week6Lab/
$ ls
[Practice.txt is gone]
$ ls ~/Documents/Week6Lab/
Practice.txt
$
```

**Move file to parent directory:**
- Type: `mv Practice.txt ../`
- Press Enter
- *Moves file up one directory level*

**Rename file (using mv):**
- Type: `mv Practice.txt NewName.txt`
- Press Enter
- *Renames the file (mv can rename or move)*

---

## TASK 7: COPY FILE USING GUI

**What this does:** We're copying a file to create a duplicate in another location. The original file stays in place.

### GUI METHOD (File Manager)

1. **Open File Manager**
   - Click the **Files** icon
   - *File Manager window opens*

2. **Navigate to source file**
   - *Navigate to **Documents/Week6Lab***
   - *You will see **Practice.txt** (or your file)*

3. **Copy the file**
   - *Right-click on **Practice.txt***
   - *A context menu appears*
   - *You will see options: "Copy", "Cut", "Delete", etc.*
   - *Click **Copy***

4. **Navigate to destination**
   - *Navigate to **Documents** folder (parent of Week6Lab)*
   - *You will see Week6Lab folder and other folders*

5. **Paste the file**
   - *Right-click in an empty area*
   - *A context menu appears*
   - *Click **Paste***
   - *A copy of Practice.txt appears in Documents*

**What you should see:**
- Practice.txt still exists in Documents/Week6Lab
- A copy of Practice.txt now exists in Documents
- Both files have the same name and content

---

## TASK 8: COPY FILE USING TERMINAL

**What this does:** We're copying a file using the `cp` command. This creates a duplicate file.

### CLI METHOD (cp command)

1. **Open Terminal**
   - Press **Ctrl + Alt + T**
   - *Terminal window opens*

2. **Navigate to source folder**
   - Type: `cd ~/Documents/Week6Lab`
   - Press Enter
   - *You're in Week6Lab folder*

3. **Copy the file**
   - Type: `cp Practice.txt ~/Documents/Practice.txt`
   - Press Enter
   - *The file is copied*
   - *No message appears - if there's no error, it worked!*

**What this command does:**
- `cp` = copy command
- `Practice.txt` = source file
- `~/Documents/Practice.txt` = destination (new name/location)

4. **Verify the copy**
   - Type: `ls ~/Documents/`
   - Press Enter
   - *You will see both Practice.txt and Week6Lab folder*

5. **Verify original still exists**
   - Type: `ls`
   - Press Enter
   - *You will see Practice.txt still in Week6Lab*

**What you should see:**
```
$ cd ~/Documents/Week6Lab
$ cp Practice.txt ~/Documents/Practice.txt
$ ls
Practice.txt
$ ls ~/Documents/
Desktop  Documents  Downloads  Practice.txt  Week6Lab
$
```

**Copy with new name:**
- Type: `cp Practice.txt Practice_backup.txt`
- Press Enter
- *Creates a copy in the same folder with a new name*

**Copy entire folder:**
- Type: `cp -r Week6Lab Week6Lab_backup`
- Press Enter
- *The `-r` means recursive (copies folder and all contents)*

---

## ACTIVITY 3: FILE PERMISSIONS AND OWNERSHIP

**Do on:** Ubuntu Linux system

**What we're doing:** We're learning how Linux file permissions work and how to change them. This is critical for security and access control.

**Goal:** Understand and manage file permissions and ownership.

**Time:** 30 minutes

---

## TASK 9: VIEW FILE PERMISSIONS

**What this does:** We're learning to read and understand the permission information that Linux shows for each file.

### CLI METHOD

1. **Open Terminal**
   - Press **Ctrl + Alt + T**
   - *Terminal window opens*

2. **Navigate to your folder**
   - Type: `cd ~/Documents/Week6Lab`
   - Press Enter

3. **View detailed file information**
   - Type: `ls -l Practice.txt`
   - Press Enter
   - *You will see detailed information about the file*

**What you should see:**
```
$ ls -l Practice.txt
-rw-r--r-- 1 student student 45 Nov 23 15:30 Practice.txt
$
```

**Breaking down the output:**
- `-rw-r--r--` = permissions (we'll explain this)
- `1` = number of hard links
- `student` = owner (user who owns the file)
- `student` = group (group that owns the file)
- `45` = file size in bytes
- `Nov 23 15:30` = date and time last modified
- `Practice.txt` = filename

**Understanding permissions: `-rw-r--r--`**

Let's break it down character by character:

```
- rw- r-- r--
│ ││  ││  ││
│ ││  ││  │└─ Others (everyone else): read only
│ ││  │└─── Group: read only
│ └└─ Owner: read and write
└──── File type (- = file, d = directory)
```

**Permission letters:**
- `r` = read (can view file)
- `w` = write (can modify file)
- `x` = execute (can run file as program)
- `-` = no permission

**Examples:**
- `rwx` = read + write + execute (full access)
- `rw-` = read + write (no execute)
- `r--` = read only
- `---` = no permissions

---

## TASK 10: CHANGE FILE PERMISSIONS (SYMBOLIC METHOD)

**What this does:** We're changing file permissions using letters (symbolic notation). This is easier to understand for beginners.

### CLI METHOD (chmod symbolic)

1. **View current permissions**
   - Type: `ls -l Practice.txt`
   - Press Enter
   - *Note the current permissions (probably `-rw-r--r--`)*

2. **Add execute permission for owner**
   - Type: `chmod u+x Practice.txt`
   - Press Enter
   - *No message appears - if no error, it worked!*

**What this command does:**
- `chmod` = change mode (permissions)
- `u+x` = user (owner) + execute permission
- `Practice.txt` = the file

3. **Verify the change**
   - Type: `ls -l Practice.txt`
   - Press Enter
   - *You will see permissions changed to `-rwxr--r--`*
   - *Notice the `x` appeared in the owner section*

**What you should see:**
```
$ ls -l Practice.txt
-rw-r--r-- 1 student student 45 Nov 23 15:30 Practice.txt
$ chmod u+x Practice.txt
$ ls -l Practice.txt
-rwxr--r-- 1 student student 45 Nov 23 15:30 Practice.txt
$
```

**More symbolic examples:**

```bash
chmod g+w Practice.txt    # Add write permission for group
chmod o-r Practice.txt   # Remove read permission for others
chmod a+x Practice.txt   # Add execute permission for all (user, group, others)
chmod u-w Practice.txt   # Remove write permission for owner
```

**Symbols explained:**
- `u` = user (owner)
- `g` = group
- `o` = others (everyone else)
- `a` = all (user + group + others)
- `+` = add permission
- `-` = remove permission
- `=` = set exact permission

---

## TASK 11: CHANGE FILE PERMISSIONS (NUMERIC METHOD)

**What this does:** We're changing file permissions using numbers. This is more compact and commonly used.

### CLI METHOD (chmod numeric)

1. **View current permissions**
   - Type: `ls -l Practice.txt`
   - Press Enter
   - *Note the current permissions*

2. **Set permissions using numbers**
   - Type: `chmod 755 Practice.txt`
   - Press Enter
   - *Permissions are changed*

**What this command does:**
- `chmod` = change mode
- `755` = permission numbers
  - First digit (7) = owner permissions
  - Second digit (5) = group permissions
  - Third digit (5) = others permissions

3. **Verify the change**
   - Type: `ls -l Practice.txt`
   - Press Enter
   - *You will see: `-rwxr-xr-x`*

**Understanding the numbers:**

**Permission values:**
- 4 = read (r)
- 2 = write (w)
- 1 = execute (x)
- Add them together:
  - 7 = 4+2+1 (read + write + execute)
  - 6 = 4+2 (read + write)
  - 5 = 4+1 (read + execute)
  - 4 = 4 (read only)
  - 0 = no permissions

**What 755 means:**
- 7 (owner) = 4+2+1 = read + write + execute
- 5 (group) = 4+1 = read + execute
- 5 (others) = 4+1 = read + execute

**What you should see:**
```
$ ls -l Practice.txt
-rwxr--r-- 1 student student 45 Nov 23 15:30 Practice.txt
$ chmod 755 Practice.txt
$ ls -l Practice.txt
-rwxr-xr-x 1 student student 45 Nov 23 15:30 Practice.txt
$
```

**Common permission values:**
- `755` = owner: full, group/others: read+execute (common for programs)
- `644` = owner: read+write, group/others: read only (common for files)
- `600` = owner: read+write, group/others: no access (private files)
- `777` = everyone: full access (NOT recommended - security risk!)

---

## TASK 12: CHANGE FILE OWNERSHIP

**What this does:** We're changing who owns a file. This is useful when files need to belong to a different user or group.

**Important:** You need sudo (administrator) privileges to change ownership.

### CLI METHOD (chown command)

1. **View current ownership**
   - Type: `ls -l Practice.txt`
   - Press Enter
   - *Note the owner and group (probably `student student`)*

2. **Change file owner**
   - Type: `sudo chown root Practice.txt`
   - Press Enter
   - *You will be asked for your password*
   - *Type your password and press Enter*
   - *Note: Password won't show on screen - this is normal!*

**What this command does:**
- `sudo` = run as administrator
- `chown` = change ownership
- `root` = new owner (root user)
- `Practice.txt` = the file

3. **Verify the change**
   - Type: `ls -l Practice.txt`
   - Press Enter
   - *You will see owner changed to `root`*

**What you should see:**
```
$ ls -l Practice.txt
-rwxr-xr-x 1 student student 45 Nov 23 15:30 Practice.txt
$ sudo chown root Practice.txt
[sudo] password for student: 
$ ls -l Practice.txt
-rwxr-xr-x 1 root student 45 Nov 23 15:30 Practice.txt
$
```

**Change owner and group:**
- Type: `sudo chown student:student Practice.txt`
- Press Enter
- *Changes both owner and group back to student*

**Change ownership recursively (for folders):**
- Type: `sudo chown -R student:student Week6Lab`
- Press Enter
- *The `-R` means recursive (changes all files in folder)*

---

## TASK 13: PRACTICAL PERMISSION SCENARIOS

**What this does:** We're practicing common permission scenarios you'll encounter in real-world situations.

### Scenario 1: Make a file private (only owner can access)

1. **Set private permissions**
   - Type: `chmod 600 Practice.txt`
   - Press Enter
   - *Only owner can read and write*

2. **Verify**
   - Type: `ls -l Practice.txt`
   - Press Enter
   - *You will see: `-rw-------`*

### Scenario 2: Make a file readable by everyone, writable by owner only

1. **Set read-only for others**
   - Type: `chmod 644 Practice.txt`
   - Press Enter
   - *Owner: read+write, others: read only*

2. **Verify**
   - Type: `ls -l Practice.txt`
   - Press Enter
   - *You will see: `-rw-r--r--`*

### Scenario 3: Make a script executable

1. **Create a simple script**
   - Type: `echo '#!/bin/bash' > myscript.sh`
   - Press Enter
   - Type: `echo 'echo "Hello World"' >> myscript.sh`
   - Press Enter

2. **Make it executable**
   - Type: `chmod +x myscript.sh`
   - Press Enter
   - *The `+x` adds execute permission for all*

3. **Run the script**
   - Type: `./myscript.sh`
   - Press Enter
   - *The script runs and displays "Hello World"*

**What you should see:**
```
$ chmod +x myscript.sh
$ ls -l myscript.sh
-rwxr-xr-x 1 student student 45 Nov 23 15:30 myscript.sh
$ ./myscript.sh
Hello World
$
```

---

## TASK 14: REFLECTION AND TROUBLESHOOTING

**What this does:** We're reflecting on what we learned and practicing troubleshooting common permission issues.

### Common Permission Issues

**Problem: Permission denied when trying to edit a file**

**Solution:**
1. Check current permissions: `ls -l filename`
2. If you're the owner, add write permission: `chmod u+w filename`
3. If you're not the owner, you may need sudo: `sudo chmod u+w filename`

**Problem: Cannot execute a script**

**Solution:**
1. Check if file has execute permission: `ls -l script.sh`
2. Add execute permission: `chmod +x script.sh`
3. Try running again: `./script.sh`

**Problem: Cannot delete a file**

**Solution:**
1. Check if you have write permission on the parent directory (not the file itself!)
2. Check directory permissions: `ls -ld foldername`
3. You need write permission on the directory to delete files in it

### Reflection Questions

1. **What's the difference between moving and copying a file?**
   - *Think about what happens to the original file*

2. **When would you use GUI vs CLI for file operations?**
   - *Consider speed, automation, and remote access*

3. **Why are file permissions important for security?**
   - *Think about what could happen if everyone had full access*

4. **What does "least privilege" mean in terms of permissions?**
   - *Research this concept - it's important for security*

---

## Screenshots to Capture for PLR

Take these screenshots for your Personal Learning Record:

**Activity 1:**
1. File Manager showing file being opened
2. Text Editor (Gedit) window with file open
3. Terminal showing `nano Practice.txt` command
4. Nano editor interface showing file content
5. Terminal showing `cat Practice.txt` output

**Activity 2:**
6. File Manager showing file being dragged (move operation)
7. Terminal showing `mv` command and result
8. File Manager showing copy operation
9. Terminal showing `cp` command and verification with `ls`
10. Terminal showing both original and copied files

**Activity 3:**
11. Terminal showing `ls -l` output with permission details
12. Terminal showing `chmod` command (symbolic method)
13. Terminal showing `ls -l` after chmod showing changed permissions
14. Terminal showing `chmod` command (numeric method)
15. Terminal showing `chown` command and result
16. Terminal showing final `ls -l` output with all permission changes

---

## Assessment Notes

### For Your PLR, Document:

**Introduction:**
- What file editing means in Linux
- Why both GUI and CLI methods are important
- What file permissions are and why they matter
- Brief overview of tasks performed

**Discussion:**
- Step-by-step explanation of editing files (GUI and CLI)
- How moving vs copying differs
- How file permissions work (read, write, execute)
- How ownership affects access
- Commands used and what they do
- When to use symbolic vs numeric permission notation

**Challenges:**
- Any errors encountered (permission denied, etc.)
- How you troubleshooted
- What you learned about Linux security
- Reflection on GUI vs CLI preferences

**Summary:**
- What you achieved
- How Linux file permissions differ from Windows
- Why understanding permissions is critical
- Real-world applications of these skills

---

## Tips for Success

**Before Starting:**
- Make sure Ubuntu is running
- Verify you have sudo access
- Create practice files in a safe location (your home directory)

**During Lab:**
- Take screenshots as you go
- Note any permission errors and how you fixed them
- Try both GUI and CLI methods
- Experiment with different permission values

**After Lab:**
- Document everything in PLR immediately
- Practice the commands regularly
- Review permission concepts
- Understand the security implications

---

## Common Issues and Solutions

**Issue:** Permission denied when editing file  
**Solution:** Check permissions with `ls -l`, add write permission with `chmod u+w filename`

**Issue:** Cannot execute a script  
**Solution:** Add execute permission: `chmod +x script.sh`

**Issue:** Cannot delete a file  
**Solution:** Check directory permissions (not file permissions) - you need write permission on the directory

**Issue:** Nano editor won't save  
**Solution:** Make sure you have write permission on the file and directory

**Issue:** chown command fails  
**Solution:** Make sure you're using `sudo` - changing ownership requires administrator privileges

---

**Practice both GUI and CLI methods to become proficient in Linux file management!**

