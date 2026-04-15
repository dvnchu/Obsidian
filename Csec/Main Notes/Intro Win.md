[[Win]]
## File System

### NTFS
Windows uses this file system aka New Technology File System
Before NTFS there was FAT16/32 (File Allocation Table) and HPFS

It is known as a journaling file system. In case of failure it can automatically repair folders/files with info in  alog file.
- Supports files larger than 4GB
- specific permissions
- compression
- Encryption
It also has Alternate Data Streams that allows files to contain more than one stream of data ($DATA)

### System 32
C:\Windows is the folder which contains the os

Inside there are a lot of folders including System32, This folder hold the files that are critical for the os.

## Users
Users can be Administrator or Standard User
To access user info: Run lusrmgr.msc

Windows introduced *User Account Control* as users are logged into their systems as local admins and users doesnt need to run with high privileges for daily driving.

When an operation requires high level the user will be prompted to confirm if they permit the operation to run.

task mng ctrl+shift+esc

## System config
MSconfig is the utility for advanced troubleshooting and startup tinkering

taskmgr does not see startup items
the only way to see them is startup folder, running shell:startup

there is also Advanced System Settings

## Computer Management
### System Tools

#### Task Scheduler
It allows to create and manage common automatized tasks at the times we specify
To view tasks go to Task Scheduler Library

#### Event Viewer
Allows us to view events that have ocurred on the computer. often used to diagnose problems and investigate actions executed on the system

![[Pasted image 20260121194410.png]]
logs 
![[Pasted image 20260121194427.png]]

#### Shared Folders
where you'll see a complete list of shared things that others can connect to

#### [[Intro Win#Users|Local Users And Groups]]

#### Performance
it has a performance monitor(perfmon)
allows to see perfo data in real time or from a log file

#### Device Manager
Allows us to view and configure the hardware.

### Storage
It hoards Windows Server Backup and Disk Management.
Just a disk utility program

### Services and Application
Here you can see all the services and their statuses.
(Services are a special type of application that runs in the background)


## msinfo32
_This tool gathers information about your computer and displays a comprehensive view of your hardware, system components, and software environment, which you can use to diagnose computer issues._"

The  information in **System Summary** is divided into three sections:

- **Hardware Resources**
- **Components**
- **Software Environment**

## Resmon
Per Microsoft, "_Resource Monitor displays per-process and aggregate CPU, memory, disk, and network usage information, in addition to providing details about which processes are using individual file handles and modules. Advanced filtering allows users to isolate the data related to one or more processes (either applications or services), start, stop, pause, and resume services, and close unresponsive applications from the user interface. It also includes a process analysis feature that can help identify deadlocked processes and file locking conflicts so that the user can attempt to resolve the conflict instead of closing an application and potentially losing data_"

## CMD
Command prompt; Interacting w/o gui

hostname
whoami
ipconfig

for help /?

netstat
net
