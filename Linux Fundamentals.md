- *First release of Linux was in 1991*
- File extensions matter in windows
- Linux decides file type based on content

# LINUX COMMANDS
-----------------------------------------------------

- su          -> switch user 
- pwd       -> present working directory
- cd          -> change directory
- cp f1 f2  -> copy files
- mv f1 f2 -> move/rename files
- updatedb -> index all files
- locate -> locates a file or directory
- adduser  -> adds a new user
- rm -> removing files and folders
		-> -R switch is required to delete directory

- strings -> print sequence of printable characters
- strings * | grep info -> search for text in a folder

- echo      - output text
- echo text > filename -> inputs text into file, overwrite
- echo text >> filename -> appends to file

- find -name filename -> returns location of file
- find -name *.extension -> returns location of all files with the extension

 - grep "info" filename -> shows the line where info is located in the file

- file filename -> returns type of filename

## chmod 
- modify permissions of file or directory

#### Permissions
X XXX XXX XXX
- 1. Directory
- 2. Owner
- 3. Group
- 4. Everyone

- 1. Read
- 2. Write
- 3. Execute

- L - Link
- D - Directory

#### Commands
- chmod +x        ->  give all permissions
- syntax -            chmod OGE
							chmod  755
converts to binary :- 111 101 101 permissions
owner -> rwx
group -> r-x
everyone -> r-x

- chown username filename -> changes owner of file, must be above the user.

## LINUX FILES
----

- /boot - bootloader
- /dev - 
- /media - hardware devices 
- /opt - user defined applications
- /bin - commands for executables
- /sbin -  system executables
- /etc - application files 
- /mnt - obsolete
- /proc - prosses ids
- /var - variable data
- /tmp - writable directory, volatile
- /root - home directory for root user 

- /etc/shadow - Contains passwords
- /etc/sudoers - Contains sudo users -> can contain vulnerabilities
- /etc/passwd - Contains users and passwords

- passwd and shadow are encrypted with sha512
## NETWORK COMMANDS
---
- ifconfig 

- ping -> sents an ICMP request to the address
	windows drops all icmp requests by default
	linux allows
	firewalls are used to drop packets -> sneak

- arp -> shows all neighbours
	mac address is hardware address
	packets are sent using mac address

- netstat -ano  -> lists all connections
	every system has ports which are used to connect systems

- route -> shows routing table - routing information

- Shortcuts:-
	ip a -> ifconfig
	ip r -> route
	ip n -> arp


# SHELL OPERATORS
----
- &      -> run commands in the background of terminal
- &&    -> combine multiple commands together in a single line
- >      -> output redirect, overwrite
- >>    -> output redirect, append

- while using &&, the second command will only run if the first command is successful


# TEXT EDITORS
----
GUI -> gedit, mouspad
CLI -> nano, vim

## Nano
---
- CTRL+O  -> save/saveas
- CTRL+X   -> exit


# BASH SCRIPTING
---
!#/bin/bash -> indicates bash file


# Privelige Escalation
---
- Escalating previlige from normal user to root user
- Allows to switch users and exploit neighbours



# SSH
----
- protocol between devices in encrypted form
- stands for Secure SHell
- means of interacting with terminal of remote machines

#### Connecting 
ssh username@ipaddress

## SCP
---
- protocol to securely copy files 
- general syntax -> scp source destination

scp filename username@ipaddress: location_to_transfer_with_filename

![[1.png]] 


# PROCESSES 
---

- Programs that are running on the machine that are managed by the kernel
- PID -> id, increments by the order which process starts
			  60th process -> PID = 60 

- ps ->  view list of running processes
- ps aux -> show system processes and processes run by other users
- top -> real-time view of all processes, refreshes every 10 seconds
- kill PID -> kill a process

- when a process is killed, we can send some signals:
	SIGTERM -> Kill the process, allow it to do cleanup tasks before
	SIGKILL -> Kill the process, without cleanup
	SIGSTOP -> Suspend a process  

#### Starting a Process
- OS uses namespaces to split up resources available
- A smaller amount of resources will be allocated to a process than what is actually available
- Namespaces isolate processes - only those processes with same namespace can will be able to see each other
- PID 0 - first process which started when system booted
			- system's init process
- PID 1 - systemd - sits between os and the user 
- All processes are controlled by systemd, but run as their own process

- Some applications can be started on boot - webservers, database servers, file transfer servers

- systemctl (option) (service) -> allows us to interact with systemd
- 4 options : start, stop, enable, disable

#### Background and Foreground 
- Process can run in two states
- echo hello -> foreground process
   echo hello & -> background process
- CTRL Z backgrounds a process
- fg -> foreground a process 


# AUTOMATION
----

- cron process can be used to automate tasks
- crontabs is used to interact with it
- It is one of the processes that is started during boot, which is responsible for facilitating and managing cron jobs.
![[crontabs.PNG]]
- * -> used for entries which we do not need
- https://crontab-generator.org/


# PACKAGE MANAGEMENT
---

- When adding software, the integrity of what we download is guaranteed by the use of what is called GPG (Gnu Privacy Guard) keys


# LOGS
---

- /var/log 
- fail2ban service -> logs attempted brute forces
- UFW service -> firewall
- Logs for web servers contain information about every single request
