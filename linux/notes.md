## CLOUDS & DEVOPS NOTES...

Introduction
===========================================================================================================================================================

# Class 1 & 2
## Possible Roles 
+ Cloud Enginerring  --> Cloud Engineering, Solutions Artchitect, Cloud Security Eng, Platform Eng
+ DeVops Enginerring --> Release Eng, Devops Engineer, Site Reliability Eng

**Tools needed for the course:**
+ WhatsApp for announcements
+ Slack for business & Course Commuinication
+ Confluence: ( documentation & processess )
+ Jira (Ticketing System for issues - Project Management)

**Devop Tools**
+ Intro to software development
+ Linux and Bash Shell Scripting
+ AWS (Amazon Web Services)
+ Terrafform
+ Kubernetes
+ Ancible
+ Jenkins + Github Action
+ Marvin
+ Docker
+ Nexus
+ Prometheus & Grafana
+ Nginx

**Cloud Computing**
+ Linux and Bash Shell Scripting
+ AWS (Amazon Web Services)
+ Terraform
+ Ansible
+ GitHub

===========================================================================================================================================================

# Class 3

+ Create EC2 Instance and login using the ssh with keypair
command: `ssh -i "keypair" ec2_instance_name`

===========================================================================================================================================================

## Class 4 - Thursday July 10th, 2025

To login to your EC2 instance USING SSH, you need an SSH Client
Examples of SSH Client options:
+ Window Powershell
+ Mac Terminal for IOS
+ Command Prompt
+ Third Party Applications like `PUTTY` etc.

We can also login into our server using : `password authenthication, ssh key pairs`

Other methods to write to a file:
+ echo "some content" > filename 
+ NB: single redirect `>` symbol means if file had some content, it would be overided by the new content. To ensure the new content does not overide the old content in the file, use the double redirect `>>`

When you create an EC2 instance with an AWS using:
Ubuntu: You get a default user and a root user
RedHat: Root user and ec2-user

===========================================================================================================================================================

class 5 - Monday July 14th, 2025
## LINUX COMMANDS
**USER MANAGEMENT COMMANDS**: Commands that control user access and permissions for security and compliance
sudo su - root : switch to the roo user. The sudo command stands for super user do which refers to someone with administrative privileges.
file `sudoer file`: contains all users with admin privilleges
`ubuntu user`: Default user that cimes with Ubuntu server and has admin prvileges. This is the user you can use to login into your server
`root user`: Root user has escalated permissions when compared to ubuntu. As security best practice, avoid using the root user as much as possible

`sudo adduser <username>`: add a new user to a server
`sudo su - username`: switch to new user created
`cat /etc/passwd`: list of users in the system, see system users
`cd /home`: verify : each user created in the ;inux OS and has his or her own home directory
`sudo deluser <username`: Delete the user
`sudo adduser <username> <group-name>`: add a suer to a group e.g sudo group. 
`sudo usermod -aG <username> <groupname>`:  create user and add them to a group
`sudo deluser <username> <groupname>`: Remove a user from a group
`sudo visudo`: view superdo file and edit
`sudo passwd <username`: Reset or change password for a user that has forgetten or compromised.
`sudo passwd -l <username>`: Locks the user account until released by admin
`sudo passwd -u <username`: unlocks the locked account
`id <username>`: Show more info on a user

steps to grant a user account access to our linux server using password
1. Open the ssh config file `sudo vi /etc/ssh/sshd_config`
2. Search for a line call `# PasswordAuthentication Yes` and uncomment the line
3. At the last line of the file, add `AllowUsers <username>` : for more control uncomment line `Match User <username>` and below it put `PasswordAuthentication yes`
4. Restart ssh using command:  `sudo systemctl restart ssh`
5. User then logins by typing : `ssh username@public DNS`

As a best security practice, allow access through user key pairs

===========================================================================================================================================================

class 6 - Tuesday July 15th, 2025
**GROUP COMMANDS**
`sudo addgroup <groupname>`: create or add a new group
`cat /etc/group`: Display all user groups
`NB`: Each time a user is created, it comes with a group which the same as the username.
`sudo delgroup <groupname`: Deletes an existing group
`sudo usermod -g <groupname> <username>`: change primary group of a user
`sudo usermod -aG <groupname> <username>`: add user to a secondary group
`groups <username>`: Displays groups a user belongs to
`sudo groupmod -n <newgroupname> <oldgroupname>`: Modify or rename a group
`gentent groups <groupname>`: provides more details about a group such if the group is external or internal

**Logging in using ssh key pairs** : Best security practice
1. Create a user if the user does not already exits : `sudo adduser <username>`
2. Create a hidden directory un the user's home directory called .ssh : `sudo mkdir -p /home/username/.ssh`
3. Set permissions for the .ssh directory using the command: `sudo chmod 700 /home/<username>/.ssh`
4. Create a file called `authorized_keys`: `sudo vi /home/<username>/.ssh/` and change permission via chmod 600``
5. Generate an ssh key pair in your local computer: `ssh-keygen` or `ssh-keygen -t rsa -b 4096 -C "comment or company-email or emailaddress" `
    + This will create a .ssh directory on the current path your are located. `cd` into .ssh and locate the public key that ends in `pub`
    + view and copy the key and sent it to the admin
    + Admin then adds the key to the authorized_key file

6. Test or ask the user ti login using the command: `ssh username@public_ip`



===========================================================================================================================================================

class 7 - Thursday July 17th, 2025

+ Question: Why is it important for a Cloud or DeVops Eng to know file and directory management
    1. Automation Insfrascture: Tools like Ansible, Terreaform and Cloudformation rely on automation scripts and configuration files. Managing this requires files management skills.
    2. Server Administration: Navigating or troubleshooting issues in servers are skills cloud engineers or devops engineers need
    3. CI/CD Pipelines: Managing credentials, configurations , log files needs file manipulations and directory navigation
    4. Security: Giving correct file permissions is essential part of Cloud or DeVops role and a lot more...

**FILE & DIRECTORY MANAGEMENT**
`ls`: list file or directories: options include `-i` (inode numbers), `-l`(more details), `-a`(show hidden files and directories)
`touch <filename>`: create a new file
`echo`: print content to console: options include echo `>` somecontent to overwrite old content and `>>` to add newcontent
`vi/vim/nano/pico`: Text editors used to modify a file. for vi/vim, exit by pressing escape then `:wq - save and quit` or `:wq! - save and force quit`
`mkdir`: make new directory
`rm`: remove file. options include `-r` and `-rf` for recursive remove for directories with content and force removal
`rmdir`: Remove empty directories


**File Permissions**
3 types of permissions are: `(r)(w)(x)` : Read, write and execute or no permission at all
Permissions can be given to 3 categories of people:
+ Users (u)  = User who created the file or any other user on the system
+ Group (g)  = Users in the same group
+ Others (o) = any other users who were not in the user or group category

Here is a breakdown:
-              rw-       rw-     r--       1             ubuntu   ubuntu    1436                 Jul 18  01:38     lcmds.txt
|               |         |       |        |               |         |        |                    |       |           |
d for dir      user     group   others  1 for files    owner      group   file_size_in_bytes      date    time     file_name
- for files                             > 1 for dir

**Changing file Permissions** `chmod`
+ File permissions can be changed Numerically (Octal Mode): Uses numbers to represent file permissions and pf the permissions rwx is assigned a numerical value: (r) = 4 , (w) = 2, (x) = 1
+ Symbolic mode: Symbolic mode uses letters and symbol to change file permissions. The format is generally like this : [who] [operator] [permissions]
   - `who`: Indicates to whom to set the permissions. It can be u(user/owner), g (group), o (others), or a (all); user, group and others
   - `Operator`: Can be `+` (to add a permission), `-` (to remove permissions), or `=` (to set exact permissions).
   - `Permissions`: read (r), write (w), execute (x)

   example: chmod u+x <filename>: adds execute permission to user group

NB: We can change the ownership of a file or directory
`chown` -`sudo chown file/directory to new_ownwer `: Change ownership of a file or dir
`sudo chgrp new_group_name file/dir ` : Change group of a file or directory
`sudo chown username:groupname < file or dir> `: Changes ownership and group of a file or dir at the same time

- To apply changes recursively to all files and dir within a given dir, use the `-R` option: chmod -R 755 <file_name or dir_name>
- Only the owner of a file or suowr user can change the permissions and ownership of a file
- You need appriopriate permissions to change the the group of a file. Generally you should be the owner of the file or superuser
- It is important to be cautious when changing the permissions and ownership, especially as a superuser,as incorrect settings can affect system security and functionality


===========================================================================================================================================================

class 8 - Monday July 21st, 2025
**Linux File Transfers**
File transfer in linux can be accomplished through several methods, depending on the requirements such as the size of the files, security or the need to transfer the files between different systens. Here are some of the most commonly ued methods for the file transfer in Linux:

*Why File Transfer Matters/ Importance of file transfer*
- We can upload and download dtata to and from cloud severs
- We can share files securely between team mates or other intergrated services on the server
- We can run back ups by transferring files from one location to another

***Different Methods of file transfer in Linux***
1. `scp (Secure Copy Protocol)`: Securely transfer files between two machines over a network using SSH. This can be transferred through two remote machines or a local remote machine

example: `scp -i optional_key_pair_id source_file_path  destination_username@destination_public_ip _address : /destination_file_path`

2. `rsync`: Synchronize files and directories between two locations with ninimal data transfer, using compression and incremental copy
syntax: `rsync [option] source (file location) target (where the file is going to )`
example: ` rsync -avz -e "ssh -i optional_key_pair" /local/dir user@remote.server.com:/remote/dir `
see rsync --help for flag options

3. SFTP : `Secure file Transfer Protocol`: Puts us in a interactive state to commuinicate back and forth between the local and remote server
- Secure: Encrypts authentication and file data using SSH
- Single Connection: Operates over one TCP connection (typically port 22).
- Interactive & Scriptable: Can be used manually or in scripts.
- Authentication: Usess SSH keys or password-based logins

`sftp <userbane@remote-servers>`: This works if you have configured ssh with your local computer and your linux sever in aws. ie copy your ssh with your computer and save in under the user .ssh in thelinux server in the file called authorized keys
`sftp -i optional_key_pair_path <username@remote-server>`: Works when key pair is not configured


get remote_file [local_file]: Downloads a file from the remote server to the local machine. You can specify a local file name if you want to rename the downloaded file. 
put local_file [remote_file]: Uploads a file from the local machine to the remote server. You can specify a remote file name if you want to rename the uploaded file. 
ls [path]: Lists the files and directories in the specified path (or the current remote directory if no path is given). 
cd path: Changes the current working directory on the remote server to the specified path. 
lcd path: Changes the current working directory on the local machine to the specified path. 
pwd: Displays the current working directory on the remote server. 
lpwd: Displays the current working directory on the local machine. 
exit or quit: Terminates the SFTP connection. 
help or ?: Displays a list of available SFTP commands. 

4. `ftp`: file transfer protocol: Transfers file between system on a network. Downside is it does not encrypt the files it transfers


===========================================================================================================================================================

class 9 - Tuesday July 22nd, 2025
**Linux File  and directory Structures**

 `/`: Root directory: The top level directory in the filesystem. All other directories are subdirectories to this
`/bin`: Contains essential binary files such as ls, cat. etc. These are fundamental commands needed in single-user mode for basic system functionality
`/opt`: Used to store additional software and packages downloaded for the system. It's a common location for software not included with the distribution package. This directory is without any content
`/boot`: Contains file necessary for system boot up, including the linux kernel. initial RAM disk image and bootloader config filed (like GRUB).
`/etc`: Houses system configuration files, system wide settings and scripts that control the behaviour of various aspects of the system:such as /etc/passwd
`/home`: This is for user and each user on the system has a directory here for personal storage, configuration etc
`lib (/lib32, /lib64)`: Contains essential shared libaries and kernel modules needed by the binaries in /bin and /sbin. These are critical for the basic functioning of the system
`/dev`: Provides a way for the system to interact with virtual servers
`/media`: Designated as mount point for removable media devices like USB drives, CD-Roms, etc
`/mnt`: Typically used as a temporarily mount point for mounting filesystem manually (used by system admins). Comes with the system and is empty
`/sbin`: Contains system admin binaries essential for booting, restoring and maintaining the system such as reboot, fdisk, fsck
`/srv`: Holds data for services provided by the system like web, FTP and others. This comes by default without any content
`/tmp`: A dir for storing temp files used by the system and applications. Files here are typically short-lived. Usually deleted after a reboot
`/usr`: One of the largest dir and contains additional apps and utilities. It has several sub-dir
    - /usr/bin: Contains user binaries and executable files.
    - /usr/inc.ude: Stores standard inculde (header) files for C abd C++ programming
    - /usr/lib: Library files for /usr/bin and /usr/sbin
    - /usr/local: local hierarchy for software installed manually ( not managed by the package manager)
    - .usr/sahre: Architecture-independent data like documentation, icons, fonts, etc
    - /usr/src: Source code usually for the `Linux Kernel`

`/var`: (Variable): Designated for files whose content is expected to grow, these includes:
    - /var/log: Logs files system log information.
    - /var/spool/: Spool for tasks like mail, printer queues and cron jobs
    - /var/cache: Cached data from app programs
    - var/lib: Dynamic data lib and files that describes the current state of installed applications
    - /var/tmp: Keeps temporary files preserved between reboots

`/root`: Stores the root user who can be the highest admin of the OS. Home directory of the root user

Package Managers for OS
- Linux : apt
- Windows: winget
- IOS: homebrew

**Hardware Management Commands**
(Hardware refer to the physical components of a computer in our case the Linux OS)
In Linux, hardware mgt involves monitoring system resources, configuring devices and troubleshooting hardware issues. There are several commands and utitilities available for managing hardware. Here's a list of commonly used hardware mgt commands in linux:

Commonly used hardware devices: CPU, memory, usb, hard disk, file systems
CPU information
`cat /proc/cpuinfo`: Provides detailed information about the CPU
`lscpu`: Provides detail info about the CPU architecture

`Memory Infomation`
`free -m`: Shows total, used and free memory in the system in MB
`cat /proc/meminfo`: Displays detailed information about the system memory

`Block Devices (Disks) Information`
`lsblk`: List all blocks (disks, USB drives, etc)
`fdisk -l`: Displays the disk partitions and their sized (requires root privilleges)
`blkid`: Shows block device attibutes (like UUID and filesystem type)

`USB devices`
`lusb`: List USB devices connected to the system

`PCI devices e.g graphic cards, sound cards`
`lspci`: List all PCI devices

`SCSI Devices - small computer system interfaces`
`lsscsi`: list SCSI devices (or host and their attributes) - Does not come installed - install with sudo apt install lsssci

`Disk Usage`
`du`: Estimates file and dir usage
`df -h`: Shows disk usage space

`Hardware Information (General)`
`lshw`: Displays detailed info* on the hardware config (requires root privilleges for detailed info)

`Graphic Informatipm`

Network Interfaces
`ifconfig`

System Architecture

**Process Management**
A process is any program or application running on a computer system.

Why is it important to deVops or cloud to know process management
- System stability and troubleshooting
- Automation and backgroud task as devops your goal is to automate tasks and run scripts so when you deploy crontabs or automated processes
- Deployment and debugging when deployment fails, checking processess can help

Viewing Processes
`top`: An interactive command that shows a real time of running processes, along with system resources usage like CPU and memory
`htop`: An enhanced version of the top command with a more user-friendly and additional features (may need to be installed seperately)
`ps`: Displays information about active processes. 
Control and Managing processes
`kill <processID>`: Terminates the current process with the process id. Typically used to gracefully stop process: example `kill 344`
`kill all`: Terminates all process with a given name, e.g killall [process_name]
`pkill`: Kills all processes based on a criteria such as `user, group, name` etc .
`xkill`: Graphical tool to terminate a misbehaving X client, when run, you can click on a window to kill its process
Managing Process Priorities
`nice`: Starts a process with a specified priority (niceness) Niceness levels range from -20 (highest) to 19 (lowest)
`renice`: Changes the priority of an already running processes e.g renice -n 10 -p [process_id]
NB: nice and renice which adjust our processes priority is important bcs it helps to 
    - Optimize your system performance: By Lowering a process priority which is less important or background process or task, 
    you ensure that critical tasks or process get more cpu time
    - Helps to avoid cpu slowdown during high cpu usage
    - It also helps to improve system responsiveness: Real time apps need fast cpu
    - This avoids your system from crashes or freezes
Process Suspension and Background Execution
Foreground: Task running in the foreground on the terminal
Background Processes: Tasks running in the background independent off the terminal, Allows you to keep running cmds on the suspended terminal while it tuns in the bg. good for long or running non-interactive tasks
`CTRL + Z`: Suspends the currently running  foreground processes
`bg`: Resumes suspended processes in the background
`fg`: Brings a background process to the foreground

**Monitoring System Activity**
`vmstat`: Reports virtual memory stats, including processes, memory, disk and CPU info
`pstree`: Displays running processess as a tree, showing their parent-child relationships

**Managing Daemon Processess (systemd Systems)**
Daemon processes: A long running background process. Typically use to provide services like logging networking and cron jobs etc
The names of daemon processes often end in the letter `d`
In LINUX, there is a process called systemd and this process is responsible for 
    - starting and managing daemon processess
    - Logging (via journald)
    - Handling dependencies btw services
    - Managing system states (boot, shutdown, sleep etc)
`systemd` process uses the `systemctl` command to control and manage these processes

systemct start [service_name]: Starts a service
systemct stop [service_name]: Stops a service
systemct restart [service_name]: restart a service
systemct status [service_name]: status of a service

Viewing Process status
`pidof`: Finds the process ID of a running program eg `pidof program name`
`pgrep`: Searches for the processes based on the name and other attributes
`ps -ef`: Displays process info for process name


===========================================================================================================================================================
class 10 - Thursday July 24th, 2025
**NETWORKING COMMANDS**
Importance of Networking Commands
- Troubleshooting Connectivity Issues
- Verifying Service Availaibility
- Working with Cloud Networking (AWS)

1. Testing Network Connectivity
`ping [address]`: It sends ICMP ECHO_REQUEST packets to network host
`traceroute [address]`: Traces the route taken by the packtes to reach the network host. May need to be installed
`tracepath [address]`: Similar to traceroute but does not require root privilleges
2. Checking Network Configuration
`ifconfig`: Displays the current network configurations for all interfaces (Note it is being depracated soon)
`ip addr show`: Shows the addresses assigned to all networks
`ip link show`: Displays the state of al network interfaces
3. Viewing and Managing route tables
`route`: Shows or modifies the IP routing table
`ip route show`: Displays the routing table
`ip route add/del [route]`: Adds or delet a route
4. Network connections and Statictics
`netstat`: Displays detail info of the current network statistic variables
5. DNS lookup
`nslookup [address]`: Queries domain name servers interactively for DNS information
`dig address`: Performs DNS lookups and displays answers.


**SSH and SCP for Secure Network**
`ssh`: Securely connects to a remote machine
`scp`: Securely transfers files between 
`hostname -i`: Displays the network address of the hostname

**Package Management Commands**
Package management refers to the methods and tools used to `install, update, configure and remove software packages` on a linux system. A package is a compressed file archive that contanins all the necessary files to install a particular software program or library, along with metadata about the package like its version, dependencies and a description of what it does.

In package management, we can install software packages using different methods
- We can use a package manager via the CLI
- Install directly on the website via GUI

`Different types of Package Managers`
*Package manager for Debian(Ubuntu, debian etc)*
- `apt or apt-get`: (Advanced Package Tool): This package manager is used for Linux distributions like Debian(Ubuntu, debian) eg: `sudo apt install nginx` - Reqs sudo privilleges
Other commands:
`sudo apt install <package_name`
` sudo apt update` | `remove` | `upgrade`| `uninstall`
*Package manager for RedHat (CentOs, Fedora, RedHat)*
`yum` is the package manager for RedHat distributions
`yum update` | `remove` | `upgrade`| `uninstall`
*DNF(Fedora 22 and newer)*
`sudo dnf install <package_name`
`dnf update` | `remove` | `upgrade`| `uninstall`

Other package managers
`snap`: Universal apcakge manager
`flatpak`: Universal package manager
`wget`: command line utitity used for downloading files from the web. Good tool that supports various protocols including HTTP, HTTPS and FTP
`brew`: Package manager for MacOS

Windows Package Managers is `Chocolatey`
choco install, remove, update <packaname>
NB: Install chocolatey on your windows os via: *https://chocolatey.org/install*

Importance of Package Management
- Security
- System Management
- Stability and Consistency




## BASH SHELL SCRIPTING
`( series / number of linux commands in a file writteh in a specific format (syntax) )`
+ It is the process of writing a series of commands in a file(script) using what is called a shell language so they can be executed as a program.
Bash shell scripts are commonly used to automate tasks in Linux and Unix-like systems such as file backups, software installations, file management, system monitoring.
`Bash - Bourne Again Shell`:  One of the most popular command line interpreters/shell used in Linux systems and unix systems.
    Bash is both a shell and a scripting language
    It allows users to interact with the OS system using of typing commands
    It is the default shell on most Linux distributions and Mac OS

`Shell`: A shell is a program that acts as an interface or intermediary between the user and the OS. It interpretes commands you type and sends them to the OS to execute. A shell can be  `Interactive: Type commands to the shell` or `Non-Interactive: Used the shell using scripts`.
examples of shells are bash shell, z shell, powershell

`Script`: Series or number of cammands in a text file written in a specific format known as syntax which can run and perform tasks automatically.
- A script is like a mini program and has instructions which needs to be executed in a sequential form or sequence e.g top to bottom
- A script needs to be executable to be able to automate tasks
- Scripts ends with the file extension `.sh`


**Importance of Bash Shell Scripting**
- Automation of repetitive tasks: By automating repetitive tasks, we save a lot of time e.g backups, deployments, user mgt, package mgt
- Efficiency: It can execute multiple cmds in a sequence without any user interaction. It reduces human errors and increases reliablilty
- Consistency: Tasks with scripts ensures that the perform the same all the time. It reduces human errors and increases reliablity.
- Flexible: It can be used to carry any kind of tasks from simple to complex tasks
- Supports version control: when changes are made to scripts, you can keep previous versions especially when managing them using tools like git and github.
- You can intergrate your scripts with CI/CD pipelines using tools like gitHub action, jenkins

**What makes a bash shell script different from other programming languages**
- Syntax - has it's own format specific to the structure
- Script execution (run the script) e.g bash <scriptname> or sh <scriptname>
- Difeerent file extensions `.sh` while python ends in `.py` and js ends in `.js`
- Bash sehll is used for automation in linux systems

**Some of the Shells out there**
1. `Bash (Bourne Again Shell)`
    - Most popular shell in linux and Mac OS
    - Dafult in most linux distributions
    - Supports scripting, automation, command history, tab completion etc
    - Extension `.sh` or `.bash`
2. ` sh (Bourne Shell)`
    - Original Unix Shell developed by `Stephen Bourne`. This has less features when compared to the modern day bash shell
3. `zsh ( Z shell)`
    - Powerful, modern shell with extra features like (auto-correction, thems via Oh My Zsh, Plugin system )
4. `ksh (KornShell)`: Developed by `David Korn` at AT & T Bell labs. It has features of the C-shell and bourne shell. It has advanced features, floating point arithmetic and associative arrays. Better than sh but less used today
5. `csh (S shell)`: Developed by `Bill Joy' at CalU. It has advanced features for interactive use and has C-like, history mechanism and job control
6. `PoweShell`
    - Build in Windows system administration
    - Object-based (outouts real objects, not plain text)
    - Windows has Command prompt
7. Others - fish, 


**Best Practices for writing Bash Shell Scripting**
1. Always start with a `shebang` - `#!bin/bash`
    This tells the system what interpreter to use. e.g `/bin/bash` for Bash (not /bin/sh) which may be linked to dash or sh
2. Ensure that your script has comments: Use comments to explain logic, for instructions (run this script only in prod, run only if you are a sudo user)
Comments could be single-line or multi-line
3. Do not hard code but instead use config files or variables
4. Ensure your script has good error handling: 
5. Ensure you handle sensitive data accurately (env) -s (passwords, tokens, ssh keys)
6. Write your scripts in modules, makes it easy to read and reuse more functions
7. Always tests your scripts in a controlled environment before using them in Prod
9. Used good naming conventions:  (naming your scripts with good names, name variables iwht good names or meaningful names)

Others
- Use maningful names
- Quote your variables e.g echo "$file_path"
- Use functions to organize your code
- Validate input and arguments
- Use loops and conditionals wisely
- Log Outputs and erros
- Saniztize inputs
- Clean up temp files


**Syntax in Bash shell scripting**
1. Shebang : #!/bin/bash
2. Comments (single and multi-line)
# This is a comment
3. Variables: Containers used to store information or data. Can be user-defined or System Variables or Environmental variables
  define variables : `variable_name="your_name"`  call variable as `$variable_name`
4. Conditonal Statements (if, else, elif)
`if`
if [condition]; then
    #code if condition is true
fi
-----------------------------------

if [condtion]; then
    # code if condition is not true
else
    # do sumn
fi
-----------------------------------
if [condition1]; then
    # do something
elif [condition2]; then
    # code if condtion2 is true
else
    #code if none are true
fi 

5. Loops (for, while, untill)
`for`: Good for files, arguments and fixed iterations
for VARIABLE in LIST
do
  COMMANDS
done

`while` : waiting for something or reading from an input
while [condition]
do 
    # do something
done

`until`: Good for retry loops, wait-until conditions
until [condition]
do 
    # commands
done

6. Aritmethic Operations: Important when you want to perform mathematical calculations in your bash shell script
### expr
results=$(expr 5 + 3)
### Double parenthesis $(( ))
results=$((5 + 3))
### Addition (sum) + Subtraction - Multiplication * , Division /, Modulus %
### Increment ++ and Decrement --
### `-eq` equal to, `-lt` less than, `-gt` greater than, `-ge` greater than or equal to, `-ne` not equal to, `-le` less than or equal to

7. Functions
AI Overview
Bash functions are reusable blocks of commands within the Bash shell environment or a Bash script. They allow grouping a set of commands to perform a specific task, which can then be executed multiple times by simply referencing the function's name. This promotes code reusability, improves script organization, and enhances readability.
Defining a Bash Function:
There are two primary syntaxes for defining a function in Bash:
- function_name () { commands }: This is the more common and generally preferred method.
    my_function () {
        echo "Hello from my function!"
        ls -l
    }
- function function_name { commands }: This syntax uses the function keyword.
    function another_function {
        echo "This is another function."
    }
Calling a Bash Function: Once defined, a function is executed by simply typing its name: my_function , another_function

8. Arrays
AI Overview
Arrays are a fundamental data structure available in the Bash shell, allowing users to store and manage multiple values within a single variable. Bash supports two primary types of arrays:
Indexed Arrays: These arrays store values in an ordered sequence, accessed using numerical indices that typically start from
Elements can be added, modified, or retrieved based on their position within the array.
Code

    # Declaring an indexed array
    my_array=("apple" "banana" "cherry")

    # Accessing an element
    echo "${my_array[0]}" # Output: apple

    # Modifying an element
    my_array[1]="grape"

    # Adding an element
    my_array[3]="orange"
Associative Arrays: These arrays store values as key-value pairs, where each value is associated with a unique string key. They are declared using declare -A.
Code

    # Declaring an associative array
    declare -A my_assoc_array
    my_assoc_array["fruit"]="apple"
    my_assoc_array["color"]="red"

    # Accessing an element
    echo "${my_assoc_array["fruit"]}" # Output: apple
Bash arrays offer flexibility, as they can store elements of different data types (e.g., strings and numbers) within the same array. While Bash supports one-dimensional arrays, it does not directly support multi-dimensional arrays or arrays as elements within other arrays. There is no inherent limit on the size of a Bash array. 

10. Input and Output
- echo : display for print content to terminal
- Redirect Output > and >>: > adds or replaces old content while

Reading from standard input is possible using the `read` command. It takes input from a user and stores it in a variable
example:  read -p "What is your name ? ___" <variable_name>
- p prompts for user input
- s option for silent input such as passwords
- n limits the number of characters: read -n 10 -p "Enter your password. _" password
 
Redirecting Input: use `<` and `<<`: for example wc < filename : This counts the number of words in a file and prints to the output

### Research: Positional parameters, case statements

## Debugging a Bash Shell Script
1. **Using "set" command options**
set -x : Enables a mode for the shell where all executed commands are printed to the terminal. This is useful for tracing the flow of the script
set -e : Causes the script to exit immediately if any command returns a non zero status
set -u : Treats unset variables as en error when performing paremter expansion
set -o pipefail : Causes the pipeline to return the exit status of the last command in the pipe that failed
2. **Using bash -x or bash -v**
This helps you to run your script in debugging options directly from the command line
`bash -x <scriptname>`: Prints each command and state as they are executed
`bash -v <scriptname>`: 
3. 
4. Adding echo statements: Using echo statements to display or print useful information on the processing status of the script.


## Exit Codes
+ exit 0: This indicates a successful completion of your script
+ exir 1: This indicates an error occurred during the execution of the scripts or command
+ exit 2: Indicates a different type of error, for example a more severe error depending on the context or command


**Some common use cases to show case experience in bash shell scripting**
+ Automate Tasks such as: Statrting and Stopping servers in `development and staging environments`
+ Create a bash shell script that rotates api keys (secret access keys) that are older than 90 days. When the script runs, it deletes the old api keys and creates a new one and then updates your local environment with the new key. To extend its functionality, you can install AWS CLI on your device using bash shell scripts and set up all its configurations
+ A script to standadize all logging in our environment
+ Back Ups scripts
+ User Mgt
+ Log retention scripts
+ CI/CD Pipelines
+ Performance Monitoring
+ Disaster Management

AWS = Amazon Web Service: A cloud provider platform that offers a range of compute resources in the cloud on demand.


### GIT & GITHUB
git is a version control systems created by the creator of the linux OS Linus Tovalds. It is a distributed version control system that helps to track changes across multiple files in a project. It enables teams work seamlessly and together on the same project.

It is considered best practice not to work on the main prod branch. What you do is create a branch off the main and work from there. Commit your changes and then submit a pull request for review and approval.


Fork: This refers to creating a copy of an existing repo on your GitHub account.



Recap
====== 

Business of Software Development

+ SDLC : Planning, Requirement Analysis, Design, Implementation, Testing and Continious Support
+ Methodology: Waterfall (Rigid) , Agile (Scrum framework, Kanban etc)
+ Development Team: People with different skillsets known as cross functional teams (DeVops Eng, SWE, Cloud Eng etc)
+ Linux OS, Bash Shell, Git & GitHub, AWS
