# Week 5 Lab Guide: Linux Users, Groups, and Permissions

Complete guide showing both GUI (Graphical User Interface) and CLI (Command Line Interface) methods.

---

## Lab Overview

### What is Week 5 About:
**Working with Linux (Ubuntu) Operating System - Users, Groups, and File Permissions**

### PC Requirements:
- **Ubuntu Linux** (Virtual Machine, lab PC, or LOD platform)
- Terminal/Shell access
- Text editor (nano or vim)
- Basic familiarity with CLI commands
- Administrator/sudo privileges

### What You'll Do:
- **Activity 1:** Explore Ubuntu using GUI and CLI, create and manage files and folders
- **Activity 2:** Create and manage Linux users and groups using command line
- **Activity 3:** Understand and configure file permissions

---

## Important Terms

| Term | Definition | Simple Explanation |
|------|------------|-------------------|
| GUI | Graphical User Interface | Using windows, icons, and mouse clicks (like Windows) |
| CLI | Command Line Interface | Typing commands in a terminal (text-based) |
| Terminal | Text-based interface for running commands | A window where you type commands |
| Shell | Command interpreter that executes commands | The program that understands your commands (usually Bash) |
| User | An account that can log into the system | Like a Windows user account |
| Group | Collection of users with shared permissions | Like a Windows security group |
| UID | User ID - unique number for each user | Every user has a number (like 1000, 1001) |
| GID | Group ID - unique number for each group | Every group has a number |
| Primary Group | Main group assigned to a user | The default group a user belongs to |
| Secondary Group | Additional groups a user can belong to | Extra groups for special access |
| Permissions | Rules that control who can read, write, or execute files | Who can do what with files |
| Root | Superuser account with full system access | Like Administrator in Windows |
| Sudo | Command to run with administrator privileges | "Super User Do" - run as admin |
| Home Directory | Personal folder for each user (/home/username) | Each user's personal files folder |

---

## Background Knowledge: Linux Basics

**What is Linux?**
- Linux is an open-source operating system (like Windows, but free)
- Ubuntu is a popular version of Linux that's user-friendly
- Linux is commonly used for servers, development, and cloud computing

**Why Learn Linux?**
- Many servers run Linux
- Essential for system administration
- Used in cloud computing (AWS, Azure, etc.)
- Important for cybersecurity and networking careers

**Key Differences from Windows:**
- Linux uses forward slashes (/) instead of backslashes (\)
- Linux is case-sensitive (File.txt ≠ file.txt)
- Linux uses commands instead of clicking (though GUI exists)
- Linux has a root user (like Administrator but more powerful)

---

## SETUP: PREPARING YOUR UBUNTU ENVIRONMENT

**What we're doing:** We need to set up Ubuntu Linux to work with. You can use a Virtual Machine, a lab PC, or an online platform.

### Option 1: Using Ubuntu Virtual Machine (Recommended)

**If you're using a VM:**

1. **Start your Ubuntu VM**
   - Open your virtualization software (VirtualBox, VMware, etc.)
   - Start the Ubuntu virtual machine
   - Wait for it to boot up

2. **Log into Ubuntu**
   - You'll see the Ubuntu login screen
   - Enter your username and password
   - Press Enter or click Sign In

3. **Verify you can access Terminal**
   - Press **Ctrl + Alt + T** (this opens Terminal)
   - OR click the Terminal icon in the launcher (left side)
   - You should see a terminal window open

**What you should see:**
- A terminal window with a prompt like: `username@computername:~$`
- The `~` means you're in your home directory
- The `$` means you're a regular user (not root)

### Option 2: Using Lab PC or Online Platform

**If using a lab PC:**
- Log into the Ubuntu system
- Open Terminal using **Ctrl + Alt + T**

**If using online platform (LOD):**
- Access the platform: https://ubuntu.com/download
- Follow the platform's instructions to access Ubuntu
- Open Terminal when ready

---

## ACTIVITY 1: LINUX OS UBUNTU

**Do on:** Ubuntu Linux system

**What we're doing:** We're learning to use Ubuntu Linux by exploring both the graphical interface (GUI) and the command line (CLI). We'll create files and folders using both methods to see the differences.

**Goal:** Explore Ubuntu using both GUI and CLI, create and manage files and folders.

**Time:** 40 minutes

---

## TASK 1: OPEN TERMINAL AND BASIC COMMANDS

**What this does:** We're learning to use the command line interface (Terminal) and basic commands to navigate and see information about the system.

**Do on:** Ubuntu Linux

### Opening Terminal

1. **Press Ctrl + Alt + T on your keyboard**
   - *This is the keyboard shortcut to open Terminal*
   - *A terminal window will open*

2. **OR click the Terminal icon in the launcher**
   - *Look at the left side of your screen (the launcher/dock)*
   - *You will see icons*
   - *Find the Terminal icon (looks like a black square or `>_` symbol)*
   - *Click it*
   - *A terminal window opens*

**What you should see:**
- A window with a black or dark background
- Text that looks like: `username@computername:~$`
- A blinking cursor waiting for you to type

### Basic Commands

**In your terminal, try these commands one by one:**

#### Command 1: `whoami`

**What this does:** Shows you which user account you're currently logged in as.

1. **Type:** `whoami`
2. **Press Enter**
3. **What you will see:**
   - The terminal will display your username
   - For example: `student` or `ubuntu` or your username
   - The prompt appears again, ready for the next command

**Example output:**
```
$ whoami
student
$
```

#### Command 2: `pwd`

**What this does:** Shows you the current directory (folder) you're in. "pwd" stands for "Print Working Directory".

1. **Type:** `pwd`
2. **Press Enter**
3. **What you will see:**
   - The terminal will display the full path to your current directory
   - Usually something like: `/home/username`
   - This is your home directory

**Example output:**
```
$ pwd
/home/student
$
```

#### Command 3: `ls`

**What this does:** Lists all files and folders in the current directory. "ls" stands for "list".

1. **Type:** `ls`
2. **Press Enter**
3. **What you will see:**
   - A list of files and folders in your current directory
   - They appear as names, one per line or in columns
   - Common folders you might see: Desktop, Documents, Downloads, etc.

**Example output:**
```
$ ls
Desktop  Documents  Downloads  Music  Pictures  Videos
$
```

#### Command 4: `ls -l`

**What this does:** Lists files with detailed information (permissions, owner, size, date).

1. **Type:** `ls -l`
2. **Press Enter**
3. **What you will see:**
   - Files listed with detailed information
   - Each line shows: permissions, owner, group, size, date, filename
   - The `-l` is called a "flag" or "option" that changes how the command works

**Example output:**
```
$ ls -l
total 24
drwxr-xr-x 2 student student 4096 Nov 23 10:00 Desktop
drwxr-xr-x 2 student student 4096 Nov 23 10:00 Documents
drwxr-xr-x 2 student student 4096 Nov 23 10:00 Downloads
$
```

**What the output means:**
- `drwxr-xr-x` = permissions (we'll learn this later)
- `student student` = owner and group
- `4096` = size in bytes
- `Nov 23 10:00` = date and time
- `Desktop` = folder name

---

## TASK 2: NAVIGATE DIRECTORIES

**What this does:** We're learning to move around the file system using commands. This is like using File Explorer in Windows, but with commands.

### Basic Navigation Commands

#### Command: `cd foldername`

**What this does:** Changes directory (moves into a folder). "cd" stands for "change directory".

1. **Type:** `cd Desktop`
2. **Press Enter**
3. **What you will see:**
   - The prompt changes to show you're in Desktop
   - It might show: `username@computername:~/Desktop$`
   - The `~/Desktop` means you're in the Desktop folder

4. **Type:** `pwd` to confirm
5. **Press Enter**
6. **What you will see:**
   - Output like: `/home/username/Desktop`
   - This confirms you're in the Desktop folder

#### Command: `cd ..`

**What this does:** Goes up one directory level (moves to the parent folder). The `..` means "parent directory".

1. **Type:** `cd ..`
2. **Press Enter**
3. **What you will see:**
   - The prompt changes back
   - You're now in the parent directory (home directory)

#### Command: `cd` or `cd ~`

**What this does:** Returns to your home directory immediately.

1. **Type:** `cd`
2. **Press Enter**
3. **What you will see:**
   - You're back in your home directory
   - The prompt shows: `username@computername:~$`

#### Command: `cd /`

**What this does:** Changes to the root directory (top level of the file system).

1. **Type:** `cd /`
2. **Press Enter**
3. **Type:** `pwd`
4. **Press Enter**
5. **What you will see:**
   - Output: `/`
   - This is the root of the entire file system

6. **Type:** `ls`
7. **Press Enter**
8. **What you will see:**
   - A list of system folders like: `bin`, `boot`, `dev`, `etc`, `home`, `usr`, etc.
   - These are important system directories

9. **Type:** `cd ~` to return home
10. **Press Enter**

#### Command: `cd -`

**What this does:** Goes back to the previous directory you were in.

1. **Type:** `cd Desktop`
2. **Press Enter**
3. **Type:** `cd -`
4. **Press Enter**
5. **What you will see:**
   - You're back in the previous directory (home)

---

## TASK 3: CREATE A FOLDER (GUI METHOD)

**What this does:** We're creating a folder using the graphical interface (like Windows File Explorer).

### GUI METHOD (File Manager)

1. **Open File Manager**
   - Click the **Files** icon in the launcher (left side)
   - OR press **Super key + N** (Super key is usually the Windows key)
   - *A File Manager window opens*

2. **Navigate to the Desired Location**
   - *In your File Manager window, you will see folders like Desktop, Documents, etc.*
   - *Double-click **Desktop** to open it*
   - *OR navigate to any folder where you want to create the new folder*

3. **Right-Click for Context Menu**
   - *In the File Manager window, right-click in an empty area*
   - *A context menu appears*
   - *You will see options like: "New Folder", "Paste", "Properties", etc.*

4. **Name Your Folder**
   - *In the context menu, click **New Folder***
   - *A new folder appears with the name "New Folder" highlighted*
   - *Type your desired name, for example: **myfolder***
   - *Press Enter*
   - *The folder is created with your chosen name*

**What you should see:**
- A new folder appears in File Manager with your chosen name
- You can double-click it to open it (it will be empty)

---

## TASK 4: CREATE A FOLDER (CLI METHOD)

**What this does:** We're creating a folder using the command line. This is faster and more powerful than using the GUI.

### CLI METHOD (Terminal)

1. **Open Terminal**
   - Press **Ctrl + Alt + T**
   - *Terminal window opens*

2. **Navigate to Desktop**
   - Type: `cd ~/Desktop`
   - Press Enter
   - *You will see the prompt change to show you're in Desktop*

3. **Create the folder**
   - Type: `mkdir myfolder`
   - Press Enter
   - *The folder is created immediately*
   - *You won't see a message - if there's no error, it worked!*

4. **Verify the folder was created**
   - Type: `ls`
   - Press Enter
   - *You will see your new folder listed: **myfolder***

**What you should see:**
```
$ cd ~/Desktop
$ mkdir myfolder
$ ls
myfolder
$
```

**Tips:**
- You can create multiple folders at once: `mkdir folder1 folder2 folder3`
- You can create nested folders: `mkdir -p parent/child/grandchild`
- The `-p` flag creates parent directories if they don't exist

---

## TASK 5: CREATE A FILE (GUI METHOD)

**What this does:** We're creating a text file using the graphical interface.

### GUI METHOD (File Manager)

1. **Open File Manager**
   - Click the **Files** icon in the launcher
   - *File Manager window opens*

2. **Navigate to Your Folder**
   - *Navigate to the folder where you want to create the file*
   - *For example, go to Desktop and open **myfolder***

3. **Right-Click for Context Menu**
   - *In the File Manager window, right-click in an empty area*
   - *A context menu appears*

4. **Create New Document**
   - *In the context menu, you will see "New Folder" and "New Document"*
   - *Click **New Document** → **Empty Document***
   - *A new file appears with the name "New Document" highlighted*

5. **Name Your File**
   - *Type your desired name, for example: **testfile.txt***
   - *Press Enter*
   - *The file is created*

**What you should see:**
- A new file appears in File Manager with your chosen name
- You can double-click it to open and edit it

---

## TASK 6: CREATE A FILE (CLI METHOD)

**What this does:** We're creating a file using the command line. This is very fast and useful for automation.

### CLI METHOD (Terminal)

1. **Open Terminal**
   - Press **Ctrl + Alt + T**
   - *Terminal window opens*

2. **Navigate to Your Folder**
   - Type: `cd ~/Desktop/myfolder`
   - Press Enter
   - *You're now in the myfolder directory*

3. **Create the file**
   - Type: `touch testfile.txt`
   - Press Enter
   - *The file is created immediately*
   - *No message appears - if there's no error, it worked!*

4. **Verify the file was created**
   - Type: `ls`
   - Press Enter
   - *You will see your new file listed: **testfile.txt***

**What you should see:**
```
$ cd ~/Desktop/myfolder
$ touch testfile.txt
$ ls
testfile.txt
$
```

**What `touch` does:**
- Creates an empty file if it doesn't exist
- Updates the timestamp if the file already exists
- Very useful for creating placeholder files

---

## TASK 7: REMOVE A FILE (GUI METHOD)

**What this does:** We're deleting a file using the graphical interface.

### GUI METHOD (File Manager)

1. **Open File Manager**
   - Click the **Files** icon in the launcher
   - *File Manager window opens*

2. **Navigate to Your File**
   - *Navigate to the folder containing the file you want to delete*
   - *For example, go to Desktop/myfolder*

3. **Delete the File**
   - *In File Manager, you will see your file (testfile.txt)*
   - *Right-click on the file*
   - *A context menu appears*
   - *Click **Move to Trash** or **Delete***
   - *The file is deleted*

**What you should see:**
- The file disappears from File Manager
- It may go to Trash (you can recover it) or be permanently deleted

---

## TASK 8: REMOVE A FILE (CLI METHOD)

**What this does:** We're deleting a file using the command line. Be careful - this is permanent!

### CLI METHOD (Terminal)

1. **Open Terminal**
   - Press **Ctrl + Alt + T**
   - *Terminal window opens*

2. **Navigate to Your Folder**
   - Type: `cd ~/Desktop/myfolder`
   - Press Enter

3. **Remove the file**
   - Type: `rm testfile.txt`
   - Press Enter
   - *The file is deleted immediately*
   - *No confirmation - be careful!*

4. **Verify the file was deleted**
   - Type: `ls`
   - Press Enter
   - *The file should no longer appear in the list*

**What you should see:**
```
$ cd ~/Desktop/myfolder
$ rm testfile.txt
$ ls
$
```

**Important Warnings:**
- `rm` deletes files permanently (no Trash/Recycle Bin)
- Be very careful with the `rm` command
- Double-check the filename before pressing Enter
- There's no "undo" for `rm`!

**Remove a folder:**
- To remove an empty folder: `rmdir foldername`
- To remove a folder with contents: `rm -r foldername`
- The `-r` means "recursive" (deletes everything inside)

---

## TASK 9: REFLECTION QUESTIONS

**After completing Activity 1, think about these questions:**

1. **What differences did you notice between using the GUI and the CLI in Ubuntu?**
   - *Think about speed, ease of use, and when you might use each method*

2. **Which method did you find more efficient or intuitive for file management? Why?**
   - *Consider your experience and preferences*

3. **What is one new command or concept you learned in this activity?**
   - *Reflect on what was new or interesting*

**Take notes of your answers - you'll use these for your PLR!**

---

## ACTIVITY 2: CREATING USERS AND GROUPS

**Do on:** Ubuntu Linux system

**What we're doing:** We're learning to create and manage user accounts and groups in Linux. This is important for system administration and security.

**Goal:** Create new users and groups, assign group membership, and verify their configuration.

**Time:** 20 minutes

---

## TASK 10: CREATE A NEW USER

**What this does:** We're creating a new user account on the Linux system. This is like creating a new user account in Windows.

**Important:** You need administrator privileges (sudo) to create users.

### CLI METHOD (Terminal)

1. **Open Terminal**
   - Press **Ctrl + Alt + T**
   - *Terminal window opens*

2. **Create a new user with basic settings**
   - Type: `sudo useradd -m -s /bin/bash devuser`
   - Press Enter
   - *You will be asked for your password (your user's password, not the new user's)*
   - *Type your password and press Enter*
   - *Note: When you type the password, nothing appears on screen - this is normal!*

**What this command does:**
- `sudo` = run as administrator (Super User Do)
- `useradd` = command to add a new user
- `-m` = create a home directory for the user
- `-s /bin/bash` = set the shell to Bash (the command interpreter)
- `devuser` = the username we're creating

**What you should see:**
```
$ sudo useradd -m -s /bin/bash devuser
[sudo] password for student: 
$
```

3. **Verify the user was created**
   - Type: `id devuser`
   - Press Enter
   - *You will see information about the user*

**What you should see:**
```
$ id devuser
uid=1001(devuser) gid=1001(devuser) groups=1001(devuser)
$
```

**What this means:**
- `uid=1001` = User ID is 1001
- `gid=1001` = Group ID is 1001 (primary group)
- `groups=1001(devuser)` = groups the user belongs to

---

## TASK 11: CREATE USER WITH SPECIFIC HOME DIRECTORY

**What this does:** We're creating a user and specifying exactly where their home directory should be located.

### CLI METHOD (Terminal)

1. **Create a user with a specific home directory**
   - Type: `sudo useradd -d /home/test_user test_user`
   - Press Enter
   - *Enter your password when prompted*

**What this command does:**
- `-d /home/test_user` = set the home directory to /home/test_user
- `test_user` = the username

2. **Verify the home directory**
   - Type: `ls -l /home/`
   - Press Enter
   - *You will see the home directories listed*

**What you should see:**
```
$ ls -l /home/
total 8
drwxr-xr-x 2 devuser devuser 4096 Nov 23 10:00 devuser
drwxr-xr-x 2 test_user test_user 4096 Nov 23 10:00 test_user
$
```

---

## TASK 12: CREATE USER WITH SPECIFIC USER ID (UID)

**What this does:** We're creating a user and assigning a specific User ID number. This is useful when you need specific UIDs for compatibility or organization.

### CLI METHOD (Terminal)

1. **Create a user with a specific UID**
   - Type: `sudo useradd -u 1234 test_user2`
   - Press Enter
   - *Enter your password when prompted*

**What this command does:**
- `-u 1234` = assign User ID 1234 to this user
- `test_user2` = the username

2. **Verify the UID**
   - Type: `id test_user2`
   - Press Enter
   - *You will see the user's information*

**What you should see:**
```
$ id test_user2
uid=1234(test_user2) gid=1234(test_user2) groups=1234(test_user2)
$
```

**Notice:** The UID is exactly 1234 as we specified!

---

## TASK 13: CREATE A GROUP

**What this does:** We're creating a group. Groups allow multiple users to share permissions and access to files.

### CLI METHOD (Terminal)

1. **Create a new group**
   - Type: `sudo groupadd developers`
   - Press Enter
   - *Enter your password when prompted*

**What this command does:**
- `groupadd` = command to add a new group
- `developers` = the group name

2. **Verify the group was created**
   - Type: `getent group developers`
   - Press Enter
   - *You will see group information*

**What you should see:**
```
$ getent group developers
developers:x:1002:
$
```

**What this means:**
- `developers` = group name
- `x` = password (encrypted, not shown)
- `1002` = Group ID (GID)
- (empty) = no members yet

---

## TASK 14: ADD USER TO A GROUP

**What this does:** We're adding a user to a group. This gives the user the permissions associated with that group.

### CLI METHOD (Terminal)

1. **Add user to a group**
   - Type: `sudo usermod -a -G developers devuser`
   - Press Enter
   - *Enter your password when prompted*

**What this command does:**
- `usermod` = modify user account
- `-a` = append (add to existing groups, don't replace)
- `-G developers` = add to the "developers" group
- `devuser` = the user to modify

**Important:** Always use `-a` flag! Without it, you'll remove the user from all other groups.

2. **Verify the user was added to the group**
   - Type: `id devuser`
   - Press Enter
   - *You will see updated group information*

**What you should see:**
```
$ id devuser
uid=1001(devuser) gid=1001(devuser) groups=1001(devuser),1002(developers)
$
```

**Notice:** The user now belongs to two groups:
- `1001(devuser)` = primary group
- `1002(developers)` = secondary group

---

## TASK 15: SET USER PASSWORD

**What this does:** We're setting a password for a user so they can log in.

### CLI METHOD (Terminal)

1. **Set password for a user**
   - Type: `sudo passwd devuser`
   - Press Enter
   - *Enter your password (sudo password)*
   - *You will be asked to enter the new password for devuser*
   - *Type the new password and press Enter*
   - *You will be asked to confirm - type it again and press Enter*

**What you should see:**
```
$ sudo passwd devuser
[sudo] password for student: 
New password: 
Retype new password: 
passwd: password updated successfully
$
```

**Important:**
- The password won't show on screen as you type (for security)
- Make sure both entries match
- Use a strong password

---

## TASK 16: VERIFY USER AND GROUP CONFIGURATION

**What this does:** We're checking that everything is set up correctly.

### Verification Commands

1. **Check user information**
   - Type: `id devuser`
   - Press Enter
   - *Shows UID, GID, and all groups*

2. **Check group members**
   - Type: `getent group developers`
   - Press Enter
   - *Shows group information and members*

3. **List all users**
   - Type: `cut -d: -f1 /etc/passwd`
   - Press Enter
   - *Shows all usernames on the system*

4. **List all groups**
   - Type: `getent group | cut -d: -f1`
   - Press Enter
   - *Shows all group names*

**What you should see:**
```
$ id devuser
uid=1001(devuser) gid=1001(devuser) groups=1001(devuser),1002(developers)

$ getent group developers
developers:x:1002:devuser

$ cut -d: -f1 /etc/passwd
root
daemon
...
student
devuser
test_user
test_user2
```

---

## ACTIVITY 3: FILE PERMISSIONS (BONUS)

**What we're doing:** Understanding how Linux file permissions work. This is important for security and collaboration.

**Note:** This is a bonus activity. The main focus is Activities 1 and 2.

### Understanding Permissions

**When you run `ls -l`, you see something like:**
```
-rwxr-xr-x 1 student student 4096 Nov 23 10:00 myfile.txt
```

**Breaking it down:**
- `-rwxr-xr-x` = permissions
  - First character: `-` = file, `d` = directory
  - Next 3: `rwx` = owner permissions (read, write, execute)
  - Next 3: `r-x` = group permissions (read, execute)
  - Last 3: `r-x` = others permissions (read, execute)
- `student student` = owner and group
- `4096` = size
- `Nov 23 10:00` = date/time
- `myfile.txt` = filename

### Change Permissions

**Command:** `chmod`

**Examples:**
- `chmod 755 myfile.txt` = owner: read/write/execute, group: read/execute, others: read/execute
- `chmod 644 myfile.txt` = owner: read/write, group: read, others: read
- `chmod 777 myfile.txt` = everyone: read/write/execute (NOT recommended for security!)

**Permission numbers:**
- 4 = read
- 2 = write
- 1 = execute
- Add them together: 7 = 4+2+1 (read+write+execute)

---

## Screenshots to Capture for PLR

Take these screenshots for your Personal Learning Record:

**Activity 1:**
1. Terminal window showing `whoami`, `pwd`, `ls` commands and outputs
2. File Manager showing folders created via GUI
3. Terminal showing `mkdir` and `touch` commands
4. Terminal showing `ls -l` output with file details
5. File Manager and Terminal side-by-side showing the same files

**Activity 2:**
6. Terminal showing `useradd` command execution
7. Terminal showing `id devuser` output showing UID and groups
8. Terminal showing `groupadd` command
9. Terminal showing `usermod` command adding user to group
10. Terminal showing `id devuser` output after adding to group (showing multiple groups)
11. Terminal showing `getent group developers` output

---

## Assessment Notes

### For Your PLR, Document:

**Introduction:**
- What Linux/Ubuntu is and why it's important
- Difference between GUI and CLI
- Why learning both methods is valuable
- Brief overview of tasks performed

**Discussion:**
- Step-by-step explanation of commands used
- Why you chose GUI vs CLI for different tasks
- How user and group management works in Linux
- Commands used and what they do
- How UID and GID work

**Challenges:**
- Any errors encountered
- How you troubleshooted
- What you learned from mistakes
- Reflection on GUI vs CLI preferences

**Summary:**
- What you achieved
- How Linux differs from Windows
- Why user and group management is important
- Next steps (learning more commands, permissions, etc.)

---

## Tips for Success

**Before Starting:**
- Make sure Ubuntu is installed and running
- Verify you have sudo/administrator access
- Take a snapshot of your VM (if using one)

**During Lab:**
- Take screenshots as you go
- Note any errors and how you fixed them
- Try both GUI and CLI methods
- Experiment with commands (safely!)

**After Lab:**
- Document everything in PLR immediately
- Keep notes of commands you found useful
- Practice the commands regularly
- Review the reflection questions

---

## Common Issues and Solutions

**Issue:** Command not found  
**Solution:** Check spelling, make sure you're typing the command correctly

**Issue:** Permission denied  
**Solution:** Use `sudo` before the command (if you have sudo access)

**Issue:** Cannot create user  
**Solution:** Make sure you're using `sudo`, check if username already exists

**Issue:** User not in group  
**Solution:** Make sure you used `-a` flag with `usermod`, verify with `id username`

**Issue:** Can't delete file  
**Solution:** Check permissions with `ls -l`, use `sudo` if needed, be careful with `rm`!

---

**Practice both GUI and CLI methods to become proficient in Linux!**

