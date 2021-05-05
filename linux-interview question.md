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


## Topic#2 : Slightly more advanced Linux:

init
====


systemd
=======


systemctl
=========


journalctl
==========


some linux philosophy, /proc filesystem)



## Topic:3 open-ended questions and troubleshooting:
top
===

atop
====

htop
=====

glances
=========

lsof 
====

proc 
====

ss or netstat 
=============

inodes
======


discussing past projects, planning a hypothetical implementation/project