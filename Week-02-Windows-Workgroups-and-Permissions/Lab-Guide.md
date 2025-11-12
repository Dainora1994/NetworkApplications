# Week 2 Lab: Complete Beginner's Guide
> Step-by-step instructions explained like you're 14 years old

![Difficulty](https://img.shields.io/badge/Difficulty-Beginner-green)
![Duration](https://img.shields.io/badge/Duration-60%20min-orange)

## 🌟 What You'll Learn Today

You're going to connect two computers together so they can share files! Think of it like creating a small network between two friends' computers. By the end, you'll be able to:

- Make two computers recognize each other
- Create user accounts (like usernames for logging in)
- Share folders between computers
- Control who can access what files

---

## 📖 Important Terms (Simple Explanations)

| Term | Simple Explanation | Real-Life Example |
|------|-------------------|-------------------|
| **Workgroup** | A group name for computers that want to share files | Like a club name - everyone in "Chess Club" can share chess books |
| **Network Discovery** | Letting your computer find other computers nearby | Like turning on your phone's Bluetooth so it can find other devices |
| **Ping** | Sending a "hello" message to another computer | Like texting "you there?" to a friend |
| **Share/Shared Folder** | A folder that other computers can access | Like a shared Google Drive folder everyone can see |
| **User Account** | A username and password to log into a computer | Like your Netflix or Instagram account |
| **Group** | A collection of users | Like putting students into Team A and Team B |
| **Permissions** | Rules about who can open, edit, or delete files | Like house rules: some people can use the kitchen, others can't |
| **GUI** | Graphical User Interface - clicking buttons (the normal way) | Using your phone by tapping icons |
| **Terminal/CMD** | Command Prompt - typing commands (the text way) | Like using text commands instead of touching icons |
| **Administrator** | A special account that can change important settings | Like a teacher having the password to school computers |

---

## 📋 What You Need Before Starting

- [ ] 2 Windows computers (we'll call them PC1 and PC2)
- [ ] Both computers connected to the same WiFi or plugged into the same network
- [ ] Administrator password (ability to change computer settings)
- [ ] About 1 hour of time
- [ ] A way to take screenshots (PrtScn button on keyboard)

---

# 🎯 ACTIVITY 1: Make Your Two PCs See Each Other

## **Goal:** Connect both computers to the same workgroup so they can find each other

---

## **STEP 1: Give Your Computers Simple Names**

Let's call them PC1 and PC2 so it's easy to remember which is which.

### **On the First Computer (PC1):**

1. **Click the Start button** - This is the Windows logo in the bottom-left corner of your screen
2. **Click the Settings icon** - Looks like a gear ⚙️, it's right above the power button
3. **Click "System"** - First big box at the top-left (has a laptop picture 💻)
4. **Scroll all the way down on the left menu**
5. **Click "About"** - It's the last option at the bottom
6. Look for **"Device specifications"** section on the right side
7. **Click the "Rename this PC" button** - It's blue
8. A small window pops up in the middle of your screen
9. **Type: PC1** in the text box
10. **Click "Next"**
11. **Click "Restart now"** - Your computer will turn off and back on (takes about 2 minutes)

### **On the Second Computer (PC2):**

**Do the exact same steps above, but:**
- In step 9, type **PC2** instead of PC1

✅ **Checkpoint:** Both computers now have clear names!

---

## **STEP 2: Put Both Computers in the Same Workgroup**

Think of this like putting them both in the same team!

### **On PC1:**

1. **Right-click the Start button** (the Windows logo bottom-left)
2. A menu pops up with lots of options
3. **Click "System"** (it's about 4th option from the top, has a laptop icon 💻)
4. The Settings window opens
5. On the right side, look for "Related settings" (blue text links)
6. **Click "Advanced system settings"** (it's a blue link)
7. A new window called "System Properties" opens
8. At the top of this window, **click the "Computer Name" tab**
9. At the bottom, **click the "Change..." button**
10. Another smaller window opens
11. You'll see two choices: "Domain" and "Workgroup"
12. **Click the circle next to "Workgroup"** (make sure it's selected)
13. In the text box next to Workgroup, **delete what's there** and type: **NetAppsLab**
   - ⚠️ **Important:** Spell it exactly like this! Capital N, capital A, capital L, no spaces
14. **Click "OK"**
15. A welcome message appears - **click "OK"**
16. Another message says you need to restart - **click "OK"**
17. **Click "Close"** on the System Properties window
18. **Click "Restart Now"**

### **On PC2:**

**Do the exact same steps!** Make sure you type **NetAppsLab** exactly the same way.

✅ **Checkpoint:** Both computers are now in the "NetAppsLab" workgroup!

---

## **STEP 3: Turn On Network Discovery**

This is like turning on your computer's radar to find other computers.

### **On BOTH PC1 and PC2 (do this on each computer):**

1. **Click the Start button**
2. **Type: Control Panel** (just start typing, you don't need to click anywhere first)
3. **Press Enter** on your keyboard
4. The Control Panel window opens
5. In the top-right corner, make sure it says "View by: Category"
6. **Click "Network and Internet"** (first box with a green globe 🌐)
7. **Click "Network and Sharing Center"** (second option)
8. On the LEFT side, **click "Change advanced sharing settings"** (blue text)
9. You'll see sections called "Private", "Guest or Public", and "All Networks"
10. **Click the down arrow ▼ next to "Private"** (if it's not already open)
11. Under the Private section, find "Network discovery"
12. **Click the circle next to "Turn on network discovery"** ⚫ changes to 🔵
13. Also **check the box** that says "Turn on automatic setup of network connected devices" ✅
14. Scroll down a little bit to "File and printer sharing"
15. **Click the circle next to "Turn on file and printer sharing"** ⚫ changes to 🔵
16. **Scroll all the way to the bottom** of the page
17. **Click "Save changes"** (bottom-right corner)

✅ **Checkpoint:** Network discovery is now ON for both computers!

---

## **STEP 4: Turn Off Firewall (Just for This Lab!)**

The firewall is like a security guard that might block our computers from talking. We'll turn it off temporarily.

⚠️ **Remember:** Turn this back ON after you finish the lab!

### **On BOTH PC1 and PC2:**

1. **Click Start**
2. **Type: firewall**
3. **Click "Windows Defender Firewall"** (has a shield icon 🛡️)
4. A window opens
5. On the LEFT side, **click "Turn Windows Defender Firewall on or off"** (second option)
6. You'll see two sections: "Private network settings" and "Public network settings"
7. Under **"Private network settings"** (top section):
8. **Click the circle next to "Turn off Windows Defender Firewall (not recommended)"** ⚫ changes to 🔵
9. **Click "OK"** at the bottom

✅ **Checkpoint:** Firewall is temporarily off so computers can talk freely!

---

## **STEP 5: Test If Computers Can Talk to Each Other**

Now let's see if PC1 can say "hello" to PC2!

### **On PC1:**

1. **Click Start**
2. **Type: cmd** (these three letters)
3. **Press Enter**
4. A black window opens - this is called "Command Prompt" or "Terminal"
5. **Type this exactly:** `ping PC2`
6. **Press Enter**
7. **Watch what happens:**

**✅ SUCCESS looks like this:**
```
Reply from PC2... bytes=32 time<1ms TTL=128
Reply from PC2... bytes=32 time<1ms TTL=128
Reply from PC2... bytes=32 time<1ms TTL=128
Reply from PC2... bytes=32 time<1ms TTL=128
```
**This means PC1 found PC2!** 🎉

**❌ FAILURE looks like this:**
```
Request timed out
Request timed out
Request timed out
Request timed out
```
**This means they can't see each other yet.** Go back and check:
- Are both computers on the same WiFi or network?
- Is the workgroup name spelled exactly the same on both? (**NetAppsLab**)
- Is network discovery turned ON on both?
- Is the firewall turned OFF on both?

### **On PC2:**

**Do the same test, but type:** `ping PC1`

✅ **Checkpoint:** Both computers can ping each other successfully!

---

## **STEP 6: Check If They Can See Each Other's Stuff**

### **Alternative Test Using File Explorer (The Easy Way):**

1. **Click the File Explorer icon** (📁 folder on the bottom bar)
   - OR press **Windows key + E** on your keyboard
2. File Explorer opens
3. On the LEFT side, **scroll down**
4. **Click "Network"** (near the bottom, has a network icon 🌐)
5. **Look in the main area**

**✅ You should see:**
- On PC1, you should see **PC2** with a computer icon
- On PC2, you should see **PC1** with a computer icon

**If you see the other computer, SUCCESS!** 🎉

**If you see "Network discovery is turned off" - go back to Step 3 and try again**

---

# 🎯 ACTIVITY 2: Create Users and Share a Folder

## **Goal:** Make a user account, put them in a group, and create a shared folder

---

## **STEP 7: Create a User Account**

We'll create a person called "User1" who can access our shared folder.

### **On PC1 Only:**

1. **Press and hold the Windows key** (on your keyboard)
2. While holding it, **press R**
3. A small box called "Run" appears in the bottom-left
4. **Type: compmgmt.msc**
5. **Press Enter** or click OK
6. A big window called "Computer Management" opens
7. On the LEFT side, look for **"Local Users and Groups"**
8. **Click the little arrow ▶** next to it (to expand it)
9. Two items appear below it: "Users" and "Groups"
10. **Click "Users"**
11. On the RIGHT side, you see a list of existing users
12. **Right-click in the EMPTY WHITE SPACE** (don't click on any existing user)
13. A menu pops up - **Click "New User..."**
14. A "New User" window opens - **Fill in the form:**

**Type exactly:**
- **User name:** `User1`
- **Full name:** (leave this empty or type anything)
- **Description:** `Test User`
- **Password:** `P@ssword123`
  - ⚠️ Use capital P, @ symbol, lowercase ssword, then 123
- **Confirm password:** `P@ssword123` (type it again exactly)

15. **Look at the checkboxes below:**
- ❌ **UNCHECK** "User must change password at next logon" (click it to remove the checkmark)
- ✅ **CHECK** "Password never expires" (click to add a checkmark)

16. **Click "Create"** (bottom-right)
17. **User1 appears in the list!** ✅
18. **Click "Close"**

✅ **Checkpoint:** User1 is created!

---

## **STEP 8: Create a Group**

A group is like a team. Instead of giving permissions to each person, we give permissions to the whole team!

### **On PC1:**

1. If Computer Management is still open, great! If not:
   - **Press Windows + R**
   - **Type: compmgmt.msc**
   - **Press Enter**
2. On the LEFT, expand **"Local Users and Groups"** (click the arrow)
3. This time, **click "Groups"** (not Users)
4. On the RIGHT, you see existing groups like "Administrators", "Users", etc.
5. **Right-click in the EMPTY WHITE SPACE** (below all the groups)
6. A menu pops up - **Click "New Group..."**
7. A "New Group" window opens
8. **Fill in:**
   - **Group name:** `ProjectTeam`
   - **Description:** `Project Team Members` (optional)
9. **Don't add any members yet** - leave that box empty
10. **Click "Create"**
11. **ProjectTeam appears in the list!** ✅
12. **Click "Close"**

✅ **Checkpoint:** ProjectTeam group is created!

---

## **STEP 9: Add User1 to the ProjectTeam Group**

Now let's put User1 into the ProjectTeam group!

### **On PC1:**

1. In Computer Management, make sure **"Groups"** is selected on the left
2. On the right, **find "ProjectTeam"** in the list
3. **Double-click "ProjectTeam"** (double-click = click twice quickly)
4. "ProjectTeam Properties" window opens
5. In the middle, you see "Members:" with an empty white box
6. At the bottom, **click the "Add..." button**
7. A "Select Users" window pops up
8. At the bottom, there's a box that says "Enter the object names to select"
9. **Click inside that box** and **type: User1**
10. **Click "Check Names"** (bottom-left of the window)
11. If you typed it correctly, "User1" gets underlined
12. **Click "OK"** (bottom-right)
13. **You're back in ProjectTeam Properties** - **User1 now appears in the Members box!** ✅
14. **Click "OK"** to close

✅ **Checkpoint:** User1 is now a member of ProjectTeam!

---

## **STEP 10: Create a Folder to Share**

Let's make a folder that both computers can access.

### **On PC1:**

1. **Click the File Explorer icon** (📁 on the bottom taskbar)
   - OR press **Windows key + E**
2. File Explorer opens
3. On the LEFT side, **click "This PC"** (has a computer icon 🖥️)
4. In the main area, you see your drives
5. **Double-click "Local Disk (C:)"**
6. You're now inside the C: drive (the address bar at top shows "This PC > Local Disk (C:)")
7. **Right-click in the EMPTY WHITE SPACE** (not on any folder)
8. A menu appears → **Hover your mouse over "New"** → A side menu appears
9. **Click "Folder"**
10. A new folder appears with the name highlighted in blue (says "New folder")
11. **Type: SharedData** (this replaces "New folder")
12. **Press Enter** on your keyboard

✅ **Checkpoint:** You now have a folder at C:\SharedData!

---

## **STEP 11: Share the Folder on the Network**

Now let's make this folder accessible from PC2!

### **On PC1:**

1. In File Explorer, make sure you're in the C:\ drive
2. **Find the "SharedData" folder** you just created
3. **Right-click the SharedData folder**
4. A big menu appears - **scroll to the bottom** and **click "Properties"**
5. "SharedData Properties" window opens with tabs at the top
6. **Click the "Sharing" tab** (3rd or 4th tab)
7. In the middle of this window, **click "Advanced Sharing"** button
8. A smaller "Advanced Sharing" window pops up
9. At the top, **check the box ✅** next to **"Share this folder"**
10. Below that, "Share name:" should already say **SharedData** (perfect! don't change it)
11. Below that, **click "Permissions"** button
12. "Permissions for SharedData" window opens
13. In the top section, you see **"Everyone"**
14. We want to remove this and add our ProjectTeam instead
15. **Click "Everyone"** to select it (it highlights in blue)
16. **Click "Remove"** button (Everyone disappears)
17. Now **click "Add"** button
18. "Select Users or Groups" window pops up
19. In the box at the bottom, **type: ProjectTeam**
20. **Click "Check Names"** - ProjectTeam gets underlined
21. **Click "OK"**
22. You're back in Permissions window
23. **Click "ProjectTeam"** in the list to select it
24. In the bottom section "Permissions for ProjectTeam":
25. **Check the box ✅** under **"Allow"** for **"Change"**
   - "Read" should automatically get checked too ✅
26. **Click "OK"** (bottom-right)
27. **Click "OK"** on the Advanced Sharing window
28. **Leave the Properties window open** (we need it for the next step)

✅ **Checkpoint:** The folder is now shared with ProjectTeam on the network!

---

## **STEP 12: Set NTFS Permissions**

This is another layer of security that controls who can actually use the files.

### **On PC1:**

**If the SharedData Properties window is still open, great! If not:**
- Right-click SharedData folder → Properties

1. At the top of the Properties window, **click the "Security" tab**
2. You see two sections:
   - Top: Lists users and groups
   - Bottom: Shows what they can do
3. In the middle, **click "Edit"** button
4. "Permissions for SharedData" window pops up
5. **Click "Add"** button (bottom-left area)
6. "Select Users or Groups" window appears
7. In the bottom box, **type: ProjectTeam**
8. **Click "Check Names"** - ProjectTeam gets underlined
9. **Click "OK"**
10. Back in Permissions window, **click "ProjectTeam"** in the top list
11. In the bottom section "Permissions for ProjectTeam":
12. **Find the row that says "Modify"** (about 3rd row down)
13. **Check the box ✅** under **"Allow"** for **"Modify"**
14. When you check Modify, several other boxes automatically check:
    - Read & execute ✅
    - List folder contents ✅
    - Read ✅
    - Write ✅
15. **Click "OK"** (bottom-right)
16. **Click "OK"** or "Close" to close the Properties window

✅ **Checkpoint:** NTFS permissions are set! ProjectTeam can now modify files!

---

# 🎯 ACTIVITY 3: Connect to the Shared Folder from PC2

## **Goal:** Access PC1's shared folder from PC2

---

## **STEP 13: Create User1 on PC2**

For this to work, PC2 needs to know about User1 too!

### **On PC2:**

**Repeat STEP 7** (Create a User Account):
- Open compmgmt.msc
- Create user "User1" with password "P@ssword123"
- Same settings as before

✅ **Checkpoint:** User1 exists on both PC1 and PC2!

---

## **STEP 14: Map the Shared Folder as a Drive Letter**

This means PC2 will see PC1's SharedData folder as if it's a drive on PC2 (like drive Z:)!

### **On PC2:**

1. **Click Start**
2. **Type: cmd**
3. **Press Enter** - Black Command Prompt window opens
4. **Type this command exactly:**
   ```
   net use Z: \\PC1\SharedData /user:PC1\User1 P@ssword123
   ```
   
**Let me explain this command:**
- `net use` = connect to a network folder
- `Z:` = call it drive Z
- `\\PC1\SharedData` = the folder on PC1 (two backslashes, then PC1, backslash, SharedData)
- `/user:PC1\User1` = login as User1 from PC1
- `P@ssword123` = the password

5. **Press Enter**

**✅ You should see:**
```
The command completed successfully.
```

**If you see an error:**
- Check that you spelled everything correctly (capital letters matter!)
- Make sure PC1 is turned on
- Make sure you can still ping PC1

---

## **STEP 15: Test the Shared Folder**

Let's see if we can actually use the shared folder!

### **On PC2:**

1. **Open File Explorer** (Windows + E)
2. **Click "This PC"** on the left
3. **Look at the main area** - you should see **Z: (\\\\PC1\\SharedData)** ✅
4. **Double-click Z:** to open it
5. You should see the empty SharedData folder!
6. **Let's create a test file:**
   - **Right-click in the empty space**
   - **New → Text Document**
   - **Name it: test.txt**
   - **Press Enter**
7. **Double-click test.txt** to open it
8. **Type: Hello from PC2!**
9. **File → Save**
10. **Close Notepad**
11. **Now try to delete it:**
    - **Right-click test.txt**
    - **Click "Delete"**

**✅ If you could create, edit, and delete the file - SUCCESS!** 🎉

This proves that:
- PC2 can access PC1's shared folder
- User1 has proper permissions
- Everything is working!

---

## **STEP 16: Test What Happens When We Remove Permission**

Let's see what happens when User1 loses access!

### **On PC1:**

1. **Open Command Prompt as Administrator:**
   - **Click Start**
   - **Type: cmd**
   - **Right-click "Command Prompt"**
   - **Click "Run as administrator"**
   - **Click "Yes"** if asked
2. **Type this command:**
   ```
   net localgroup ProjectTeam User1 /delete
   ```
3. **Press Enter**
4. You should see: "The command completed successfully."

**This removes User1 from the ProjectTeam group!**

### **On PC2:**

1. **Go to File Explorer**
2. **Try to open Z: drive**
3. **Try to create a new file**

**❌ You should get an error: "Access is denied"** or "You do not have permission"

**✅ This proves permissions are working!** When User1 was removed from ProjectTeam, they immediately lost access!

---

# 📸 IMPORTANT: Take Screenshots!

For your assignment (PLR), you need to take these screenshots:

## Screenshots to Take:

### From PC1:
1. System Properties showing Workgroup = "NetAppsLab"
2. Command Prompt with successful `ping PC2`
3. Computer Management showing User1 created
4. Command Prompt showing `net localgroup ProjectTeam` with User1 listed
5. SharedData Properties - Sharing tab
6. SharedData Properties - Security tab

### From PC2:
7. Command Prompt with successful `net use Z:` command
8. File Explorer showing Z: drive
9. test.txt file in Z: drive
10. "Access Denied" error message

**How to take screenshots:**
- Press **PrtScn** button on keyboard (copies whole screen)
- OR press **Windows + Shift + S** (lets you select an area)
- Paste into Paint or Word

---

# ✅ Lab Complete Checklist

Congratulations! Check off what you've accomplished:

- [ ] Both PCs renamed to PC1 and PC2
- [ ] Both PCs in workgroup "NetAppsLab"
- [ ] Network Discovery enabled on both
- [ ] Firewall temporarily disabled
- [ ] Can ping between both PCs
- [ ] User1 created on PC1
- [ ] ProjectTeam group created
- [ ] User1 added to ProjectTeam
- [ ] SharedData folder created
- [ ] Folder shared with ProjectTeam
- [ ] NTFS permissions set for ProjectTeam
- [ ] User1 created on PC2
- [ ] Z: drive mapped on PC2
- [ ] Can create/edit/delete files on Z:
- [ ] Access denied works when user removed
- [ ] All screenshots taken

---

# 🎓 What You Learned

You now know how to:

✅ Set up a peer-to-peer network (workgroup)  
✅ Enable computers to see each other  
✅ Create user accounts  
✅ Create groups and add users to them  
✅ Share folders on a network  
✅ Set permissions (both Share and NTFS)  
✅ Map network drives  
✅ Test and troubleshoot access control  

**These are real IT skills used in businesses every day!** 🎉

---

# ⚠️ Remember: Turn Firewall Back ON!

**On BOTH PC1 and PC2:**
1. Start → firewall
2. Click "Turn Windows Defender Firewall on or off"
3. Select "Turn on Windows Defender Firewall"
4. Click OK

---

# ❓ Troubleshooting Common Problems

| Problem | What to Check | Solution |
|---------|--------------|----------|
| Can't ping other PC | Are both on same network? | Check WiFi/cable connection |
| | Same workgroup name? | Must be spelled exactly the same |
| | Firewall off? | Temporarily disable firewall |
| Can't see PC in Network | Network Discovery on? | Go back to Step 3 |
| Access Denied to share | User in correct group? | Check group membership |
| | Permissions set correctly? | Review Steps 11-12 |
| "Network path not found" | Is other PC on? | Make sure PC1 is running |
| | Can you ping it? | Test with ping command |

---

**Need more help?**
- Check the [Troubleshooting Guide](../Resources/troubleshooting.md)
- Look up terms in the [Glossary](../Resources/glossary.md)
- Ask your instructor!

---

**Great job completing the lab!** 🎉👏

Now document everything in your PLR (Personal Learning Record) for your assessment!

