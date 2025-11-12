# Week 2 Quick Reference - Command Cheat Sheet

![Quick Reference](https://img.shields.io/badge/Type-Cheat%20Sheet-brightgreen)

> 📋 Keep this page open during your lab for quick command lookups!

---

## 🖥️ Network Commands

| Task | Command | Example |
|------|---------|---------|
| Check computer name | `hostname` | `hostname` |
| Check IP address | `ipconfig` | `ipconfig` |
| Check detailed IP info | `ipconfig /all` | `ipconfig /all` |
| Release IP address | `ipconfig /release` | `ipconfig /release` |
| Renew IP address | `ipconfig /renew` | `ipconfig /renew` |
| Flush DNS cache | `ipconfig /flushdns` | `ipconfig /flushdns` |
| Ping another computer | `ping <computername>` | `ping PC2` |
| Ping with count | `ping -n <count> <target>` | `ping -n 10 PC2` |
| Continuous ping | `ping -t <target>` | `ping -t PC2` |
| Trace route | `tracert <target>` | `tracert PC2` |
| View shared folders | `net view \\<computername>` | `net view \\PC2` |
| View ARP cache | `arp -a` | `arp -a` |
| View active connections | `netstat -an` | `netstat -an` |
| View routing table | `route print` | `route print` |

---

## 👤 User Management Commands

| Task | Command | Example |
|------|---------|---------|
| Create user | `net user <username> <password> /add` | `net user User1 P@ssword123 /add` |
| Delete user | `net user <username> /delete` | `net user User1 /delete` |
| List all users | `net user` | `net user` |
| View user details | `net user <username>` | `net user User1` |
| Change password | `net user <username> <newpassword>` | `net user User1 NewPass123` |
| Activate user | `net user <username> /active:yes` | `net user User1 /active:yes` |
| Deactivate user | `net user <username> /active:no` | `net user User1 /active:no` |
| Set password never expires | `net user <username> /passwordreq:no` | `net user User1 /passwordreq:no` |

### PowerShell User Commands

| Task | PowerShell Command |
|------|-------------------|
| List all local users | `Get-LocalUser` |
| Get user details | `Get-LocalUser -Name User1` |
| Create user | `New-LocalUser -Name "User1" -Password (ConvertTo-SecureString "P@ssword123" -AsPlainText -Force)` |
| Delete user | `Remove-LocalUser -Name "User1"` |
| Check current user | `whoami` |
| View user SID | `whoami /user` |
| View user groups | `whoami /groups` |

---

## 👥 Group Management Commands

| Task | Command | Example |
|------|---------|---------|
| Create group | `net localgroup <groupname> /add` | `net localgroup ProjectTeam /add` |
| Delete group | `net localgroup <groupname> /delete` | `net localgroup ProjectTeam /delete` |
| Add user to group | `net localgroup <group> <user> /add` | `net localgroup ProjectTeam User1 /add` |
| Remove user from group | `net localgroup <group> <user> /delete` | `net localgroup ProjectTeam User1 /delete` |
| List all groups | `net localgroup` | `net localgroup` |
| List group members | `net localgroup <groupname>` | `net localgroup ProjectTeam` |
| Add comment to group | `net localgroup <group> /comment:"description"` | `net localgroup ProjectTeam /comment:"Project Members"` |

### PowerShell Group Commands

| Task | PowerShell Command |
|------|-------------------|
| List all groups | `Get-LocalGroup` |
| Get group details | `Get-LocalGroup -Name "ProjectTeam"` |
| Get group members | `Get-LocalGroupMember -Group "ProjectTeam"` |
| Create group | `New-LocalGroup -Name "ProjectTeam"` |
| Add user to group | `Add-LocalGroupMember -Group "ProjectTeam" -Member "User1"` |
| Remove user from group | `Remove-LocalGroupMember -Group "ProjectTeam" -Member "User1"` |

---

## 📁 File & Folder Commands

| Task | Command | Example |
|------|---------|---------|
| Create folder | `mkdir <foldername>` | `mkdir C:\SharedData` |
| Delete folder | `rmdir <foldername>` | `rmdir C:\SharedData` |
| Delete folder (with contents) | `rmdir /s <foldername>` | `rmdir /s C:\SharedData` |
| List files/folders | `dir` | `dir C:\` |
| List with details | `dir /a` | `dir /a C:\` |
| Change directory | `cd <path>` | `cd C:\SharedData` |
| Copy file | `copy <source> <destination>` | `copy file.txt C:\SharedData\` |
| Move file | `move <source> <destination>` | `move file.txt C:\SharedData\` |
| Delete file | `del <filename>` | `del test.txt` |
| Rename file/folder | `rename <old> <new>` | `rename oldname.txt newname.txt` |

---

## 🌐 Sharing & Permission Commands

### Share Management

| Task | Command | Example |
|------|---------|---------|
| Share folder | `net share <sharename>=<path> /grant:<user>,<permission>` | `net share SharedData=C:\SharedData /grant:ProjectTeam,CHANGE` |
| Share with multiple permissions | `net share <name>=<path> /grant:<user1>,CHANGE /grant:<user2>,READ` | `net share Data=C:\Data /grant:User1,CHANGE /grant:User2,READ` |
| Remove share | `net share <sharename> /delete` | `net share SharedData /delete` |
| List all shares | `net share` | `net share` |
| View share details | `net share <sharename>` | `net share SharedData` |

**Permission Levels for Shares:**
- `READ` - View files only
- `CHANGE` - Read, write, delete files
- `FULL` - Full control (change permissions)

### NTFS Permissions (icacls)

| Task | Command | Example |
|------|---------|---------|
| View permissions | `icacls "<path>"` | `icacls "C:\SharedData"` |
| Grant permissions | `icacls "<path>" /grant <user>:<permission>` | `icacls "C:\SharedData" /grant User1:M` |
| Grant with inheritance | `icacls "<path>" /grant <user>:(OI)(CI)<perm>` | `icacls "C:\SharedData" /grant ProjectTeam:(OI)(CI)M` |
| Deny permissions | `icacls "<path>" /deny <user>:<permission>` | `icacls "C:\SharedData" /deny User1:W` |
| Remove permissions | `icacls "<path>" /remove <user>` | `icacls "C:\SharedData" /remove User1` |
| Reset permissions | `icacls "<path>" /reset` | `icacls "C:\SharedData" /reset` |
| Save permissions to file | `icacls "<path>" /save <file>` | `icacls "C:\SharedData" /save perms.txt` |
| Restore permissions | `icacls "<path>" /restore <file>` | `icacls "C:\SharedData" /restore perms.txt` |

**Permission Codes:**
- `F` - Full control
- `M` - Modify
- `RX` - Read & execute
- `R` - Read-only
- `W` - Write-only
- `D` - Delete

**Inheritance Flags:**
- `(OI)` - Object inherit (files)
- `(CI)` - Container inherit (folders)
- `(IO)` - Inherit only
- `(NP)` - Don't propagate inherit

---

## 🗺️ Network Drive Mapping

| Task | Command | Example |
|------|---------|---------|
| Map drive | `net use <drive>: \\<computer>\<share>` | `net use Z: \\PC1\SharedData` |
| Map with credentials | `net use <drive>: \\<computer>\<share> /user:<user> <pass>` | `net use Z: \\PC1\SharedData /user:PC1\User1 P@ssword123` |
| Map persistent drive | `net use <drive>: \\<computer>\<share> /persistent:yes` | `net use Z: \\PC1\SharedData /persistent:yes` |
| View mapped drives | `net use` | `net use` |
| Disconnect drive | `net use <drive>: /delete` | `net use Z: /delete` |
| Disconnect all drives | `net use * /delete` | `net use * /delete` |
| Disconnect without prompt | `net use * /delete /yes` | `net use * /delete /yes` |

---

## 🔥 Firewall Commands

| Task | Command |
|------|---------|
| Turn off firewall (Private) | `netsh advfirewall set privateprofile state off` |
| Turn on firewall (Private) | `netsh advfirewall set privateprofile state on` |
| Turn off firewall (Public) | `netsh advfirewall set publicprofile state off` |
| Turn on firewall (Public) | `netsh advfirewall set publicprofile state on` |
| Turn off all firewalls | `netsh advfirewall set allprofiles state off` |
| Turn on all firewalls | `netsh advfirewall set allprofiles state on` |
| Enable Network Discovery | `netsh advfirewall firewall set rule group="Network Discovery" new enable=Yes` |
| Enable File Sharing | `netsh advfirewall firewall set rule group="File and Printer Sharing" new enable=Yes` |
| View firewall status | `netsh advfirewall show allprofiles` |
| Reset firewall to default | `netsh advfirewall reset` |

---

## 🔧 Service Management

### Using net commands

| Task | Command | Example |
|------|---------|---------|
| Start service | `net start <servicename>` | `net start LanmanServer` |
| Stop service | `net stop <servicename>` | `net stop LanmanServer` |
| View service status | `sc query <servicename>` | `sc query LanmanServer` |

### Using PowerShell

| Task | PowerShell Command |
|------|-------------------|
| View service | `Get-Service <name>` |
| Start service | `Start-Service <name>` |
| Stop service | `Stop-Service <name>` |
| Restart service | `Restart-Service <name>` |
| Set service to auto-start | `Set-Service <name> -StartupType Automatic` |
| List all services | `Get-Service` |
| List running services | `Get-Service | Where-Object {$_.Status -eq "Running"}` |

**Important Network Services:**
- `LanmanServer` - File and Printer Sharing (Server service)
- `LanmanWorkstation` - Network Connections (Workstation service)
- `Dnscache` - DNS Client
- `Browser` - Computer Browser

---

## 💻 Computer Management

| Task | Command |
|------|---------|
| Rename computer | `Rename-Computer -NewName "PC1"` |
| Restart computer | `Restart-Computer` |
| Shutdown computer | `Stop-Computer` |
| View system info | `systeminfo` |
| View computer name | `hostname` |
| Change workgroup | `wmic computersystem where name="%computername%" call joindomainorworkgroup name="NetAppsLab"` |
| View workgroup/domain | `wmic computersystem get domain` |
| Open Computer Management | `compmgmt.msc` |
| Open Services | `services.msc` |
| Open Local Security Policy | `secpol.msc` |
| Open Event Viewer | `eventvwr.msc` |

---

## 🔍 Troubleshooting Commands

| Task | Command | Purpose |
|------|---------|---------|
| Test DNS resolution | `nslookup <hostname>` | Check if DNS is working |
| Test connectivity | `ping <target>` | Check if host is reachable |
| Trace network path | `tracert <target>` | Show route packets take |
| View network config | `ipconfig /all` | See all network settings |
| View open ports | `netstat -an` | See what ports are listening |
| View network connections | `netstat -ano` | See connections with PIDs |
| Test if port is open | `Test-NetConnection -ComputerName PC2 -Port 445` | PowerShell port test |
| Check SMB shares | `net view \\<computer>` | List shared folders |
| View event logs | `Get-EventLog -LogName System -Newest 50` | Check system logs |
| Clear ARP cache | `arp -d` | Clear address resolution cache |

---

## 🎯 Common Task Combinations

### Create user, add to group, set permissions

```cmd
net user User1 P@ssword123 /add
net localgroup ProjectTeam /add
net localgroup ProjectTeam User1 /add
mkdir C:\SharedData
net share SharedData=C:\SharedData /grant:ProjectTeam,CHANGE
icacls "C:\SharedData" /grant ProjectTeam:(OI)(CI)M
```

### Map drive with credentials

```cmd
net use Z: \\PC1\SharedData /user:PC1\User1 P@ssword123 /persistent:yes
```

### Enable network discovery and file sharing

```cmd
netsh advfirewall firewall set rule group="Network Discovery" new enable=Yes
netsh advfirewall firewall set rule group="File and Printer Sharing" new enable=Yes
netsh advfirewall set privateprofile state off
```

### Check network connectivity

```cmd
ping PC2
net view \\PC2
tracert PC2
Get-Service LanmanServer
Get-Service LanmanWorkstation
```

---

## 💡 Tips & Tricks

### Command Prompt Shortcuts
- **Up Arrow** - Recall previous command
- **Tab** - Autocomplete file/folder names
- **Ctrl + C** - Stop current command
- **Right-click** - Paste
- **F7** - View command history
- **cls** - Clear screen

### PowerShell Shortcuts
- **Ctrl + Space** - Show available parameters
- **Tab** - Autocomplete commands
- **Get-Command *keyword*** - Find commands
- **Get-Help <command>** - View help for command
- **Get-History** - View command history

### Useful Aliases
- `cd` = `Set-Location`
- `dir` = `Get-ChildItem`
- `cls` = `Clear-Host`
- `copy` = `Copy-Item`
- `move` = `Move-Item`
- `del` = `Remove-Item`

---

## 📝 Examples for This Week's Lab

### Complete Activity 1 (Network Setup)

```cmd
REM Check computer name
hostname

REM Ping other computer
ping PC2

REM View shared resources
net view \\PC2

REM Check network services
Get-Service LanmanServer
Get-Service LanmanWorkstation
```

### Complete Activity 2 (Users & Permissions)

```cmd
REM Create user
net user User1 P@ssword123 /add

REM Create group
net localgroup ProjectTeam /add

REM Add user to group
net localgroup ProjectTeam User1 /add

REM Verify
net localgroup ProjectTeam

REM Create and share folder
mkdir C:\SharedData
net share SharedData=C:\SharedData /grant:ProjectTeam,CHANGE
icacls "C:\SharedData" /grant ProjectTeam:(OI)(CI)M
```

### Complete Activity 3 (Map Drive)

```cmd
REM Map network drive
net use Z: \\PC1\SharedData /user:PC1\User1 P@ssword123

REM View mapped drives
net use

REM Test access by creating file
echo Test > Z:\test.txt

REM Remove user from group (on PC1)
net localgroup ProjectTeam User1 /delete

REM Disconnect drive
net use Z: /delete
```

---

## 🆘 Emergency Commands

**If something goes wrong:**

```cmd
REM Reset network settings
netsh int ip reset
netsh winsock reset
ipconfig /flushdns
ipconfig /release
ipconfig /renew

REM Restart network services
net stop LanmanServer
net start LanmanServer
net stop LanmanWorkstation
net start LanmanWorkstation

REM Remove all mapped drives
net use * /delete /yes

REM Turn firewall back on
netsh advfirewall set allprofiles state on
```

---

## 📌 Remember!

- Commands are **NOT case-sensitive** in CMD
- Use **quotes** around paths with spaces: `"C:\My Folder\"`
- Use **double backslashes** for UNC paths: `\\PC1\Share`
- Run Command Prompt **as Administrator** for system changes
- Press **Ctrl + C** to cancel a running command
- Type `help <command>` for more information about any command

---

**💾 Save this page!** You'll use these commands throughout the course!

**🔖 Pro tip:** Print this page or keep it open on a second screen during labs!

