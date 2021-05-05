# Linux for devops:
## Topic#1 Basic Linux Interview Questions 
ssh
===

SSH (Secure Shell) is a network protocol that enables secure remote connections between two systems

ls
==

list of files/folders presnt in the current location

cd
==
Change directory

cp
==

Copying the file from source to directory

pwd
===

displays current location

rsync
======

scp provides a cp like method to copy files from one machine to a remote machine over a secure SSH connection. rsync allows you to syncronise remote folders. 
They are different programs and both have their uses. scp is always secure, whereas rsync must travel over SSH to be secure.

![image](https://user-images.githubusercontent.com/54719289/117195040-b4a42a00-addc-11eb-9944-1ca7c415a8d8.png)
![image](https://user-images.githubusercontent.com/54719289/117195125-d30a2580-addc-11eb-97af-3d27d1494e0e.png)


systemctl
=========
The systemctl command is a new tool to control the systemd system and service. This is the replacement of old SysV init system management

using this command, we can enable ,start ,restart and stop the services.

df
===

Disk file
used to display the disk space used in the file system. The 'df' stands for "disk filesystem." 
It defines the number of blocks used, the number of blocks available, and the directory where the file system is mounted.

![image](https://user-images.githubusercontent.com/54719289/117196602-993a1e80-adde-11eb-886b-f6b3af02868c.png)

du
==
du command, short for “disk usage” reports the estimated amount of disk space used by given files or directories. 
It is practically useful for finding files and directories taking up large amounts of disk space

![image](https://user-images.githubusercontent.com/54719289/117196841-ed450300-adde-11eb-897c-a4e3526a2b69.png)


ip addr 
=======

To list all network interfaces and the associated IP address, use the command: ip addr show.

ip route: Gateway
================

displays the entries in the routing table, as well as the means by which they were determined 
(directly connected network, static route, or which routing protocol was used to select the route).

![image](https://user-images.githubusercontent.com/54719289/117196947-14033980-addf-11eb-9a11-6cfb6b791d76.png)


chmod:
=====
chmod is the command and system call used to change the access permissions of file system objects (files and directories) sometimes known as modes. ... The name is an abbreviation of change mode.

For ex: chmod a+x /entrypoint.sh    ==> all users have permission to exeucte the file
        chmod u+x    ==> the user who owns has execution permission
        chmod g+x   ==> the other user in the group has ececution permission
        chmod o+x   ==> the other user who is not in the group has ececution permission
        
the user who owns it (u), 
other users in the file's group (g), 
other users not in the file's group (o), 
or all users (a)

## Topic#2 : Slightly more advanced Linux:

init
====

special process that linux kernal starts that init is reponsible for starting all services and units.Also responsible for repairing 

The init is a daemon process which starts as soon as the computer starts and continue running till, it is shutdown


systemd
=======

Systemd provides a standard process for controlling what programs run when a Linux system boots up
systemd – A init replacement daemon designed to start process in parallel, implemented in a number of standard distribution.


systemctl
=========

The systemctl command is a new tool to control the systemd system and service(start/restart/stop)


journalctl
==========

Journalctl is a utility for querying and displaying logs from journald, systemd's logging service. Since journald stores log data in a binary format instead of a plaintext format, journalctl is the standard way of reading log messages processed by journald.

![image](https://user-images.githubusercontent.com/54719289/117200493-73634880-ade3-11eb-8eee-c28d20e4747c.png)


some linux philosophy, /proc filesystem)

/proc:
=====

The /proc directory is a strange beast. It doesn't really exist, yet you can explore it. Its zero-length files are neither binary nor text, yet you can examine and display them. This special directory holds all the details about your Linux system, including its kernel, processes, and configuration parameters

/proc is a virtual filesystem. You will need to write a kernel module that creates the appropriate structures within it. Ignacio Vazquez-Abrams's answer is correct: files under /proc and /sys are provided by the kernel. If you want to add a file there, write a kernel module.

## Topic:3 open-ended questions and troubleshooting:
top
===

top command displays processor activity of your Linux box and also displays tasks managed by kernel in real-time. It'll show processor and memory are being used and other information like running processes. This may help you to take correct action

atop
====

Atop is an ASCII, full-screen performance monitor which can log and report the activity of all server processes. One feature I really like is that atop stays active in the background for long-term server analysis (up to 28 days by default). ... Shows resource usage of all processes, even those that are closed or completed

htop
=====
htop is an interactive system-monitor process-viewer and process-manager. It is designed as an alternative to the Unix program top. It shows a frequently updated list of the processes running on a computer, normally ordered by the amount of CPU usage.


glances
=========

 Glances is a cross-platform command-line curses-based system monitoring tool written in Python language which use the psutil library to grab informations from the system. With Glance, we can monitor CPU, Load Average, Memory, Network Interfaces, Disk I/O, Processes and File System spaces utilization.


lsof 
====

lsof command is mainly used to retrieve information about files that are opened by various processes. Open files in a system can be of different type like disk files, network sockets, named pipes and devices. This distinctive feature enables one to debug and understand Linux Operating System in a better way.

![image](https://user-images.githubusercontent.com/54719289/117205990-364e8480-adea-11eb-94ce-52b72854bd26.png)

![image](https://user-images.githubusercontent.com/54719289/117205799-fe474180-ade9-11eb-9cad-040892fffca6.png)

ss or netstat 
=============

Netstat is a command-line network utility used to display network connections for the TCP/UDP,  network protocol statistics, interface statistics, routing tables, masquerade connections, multicast memberships e.t.c. netstat program is obsolete and its replacement is ss. Some netstat commands have been replaced by ss commands, for example:


                 $ netstat -r   replaced by   $ ip route
                 $ netstat -i   replaced by   $ ip -s lin
                 $ netstat -g   replaced by   $ ip maddr.


ss is a utility used to investigate sockets in Linux and Unix systems. It shows information similar to netstat and able to dump socket statistics. ss command can display more than TCP and state information as compared to other tools. By default, ss displays a list of open non-listening sockets (e.g. TCP/UNIX/UDP) that have established a connection.

netstat Commands:

        Common command line options used with netstat command are:
        
        -l, –listening display listening server sockets
        -a, –all display all sockets (default: connected)
        -r, –route display routing table
        –i, –interfaces display interface table
        -g, –groups display multicast group memberships
        -s, –statistics display networking statistics (like SNMP)
        -M, –masquerade display masqueraded connections
        -v, –verbose be verbose
        -W, –wide don’t truncate IP addresses
        -n, –numeric don’t resolve names
        -e, –extend display other/more information
        -p, –programs display PID/Program name for sockets
        -o, –timers display timers
        -F, –fib display Forwarding Information Base (default)
        -C, –cache display routing cache instead of FIB
        
        
  ss commands:
  
        Common options used with ss command are:
        –n, –numeric don’t resolve service names
        -r, –resolve : resolve host hostnames.
        -l, –listening display listening sockets
        -o, –options show timer information
        -e, –extended show detailed socket information
        -m, –memory show socket memory usage
        -p, –processes show process using socket
        –s, –summary show socket usage summary
        -N, –net switch to the specified network namespace name
        -4, –ipv4 display only IP version 4 sockets
        -6, –ipv6 display only IP version 6 sockets
        –0, –packet display PACKET sockets
        -t, –tcp display only TCP sockets
        -S, –sctp display only SCTP sockets
        -u, –udp display only UDP sockets
        -w, –raw display only RAW sockets
        -x, –unix display only Unix domain sockets
        -f, –family=FAMILY display sockets of type FAMILY

![image](https://user-images.githubusercontent.com/54719289/117206103-53835300-adea-11eb-9036-d43cded7ae77.png)
![image](https://user-images.githubusercontent.com/54719289/117206225-7f063d80-adea-11eb-8a54-c7a94c067c88.png)



inodes
======

An inode is a data structure used to keep information about a file on your hosting account. The number of inodes indicates the number of files and folders you have. This includes everything on your account, emails, files, folders, anything you store on the server.


discussing past projects, planning a hypothetical implementation/project

# How do you configure and infrastructure structure settings.
