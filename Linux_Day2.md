## Linux Day 2 Markdown notes and Tasks  

# Commands of linux continues 

ls - check files 

cat <.txt file> - what is inside file 

cat chicken-joke,txt | grep chicken/the - locate all lines that contains word

apt - installs packages on linux machine  insta

sudo apt install tree - install app tree, sometimes cannot install package. needs to know souce list.

sudo apt-get update -y - update and say yes to all questions: do the update first before installing packages 

cd / - root directory 

cd adminuser - home director

cd - home folder

cd ~ home folder

tree - to see structure of pwd

mv - move file

mkdir - make new folder

rm - r -recursive (IMPORTANT COMMAND, WILL REMOVE FOLDERS)

touch - make new file

nano - 

ls -l - check ownership of files 

conclusion: navigate files and folders, new command prompts.

############################ scripting ######################################
# running and making scripts 

script shell files end in (sh)

make a new file 

touch provision.sh

ls -l check ownership (rw)

path to bash shell: /bin/bash

open new gitbash and try script commands before saving on bash 

# First script automation

#!/bin/bash

update -ensure source list is upto date

sudo apt update -y

upgrade -install lastest package in linux; there are situations where upgrade isnt  req

sudo apt upgrade -y

install nginx (sudo systemctl status nginx - to check - ctl z to come out and enter)

sudo apt install nginx -y

restart nginx

sudo systemctl restart nginx

enable nginx - when VM start/stops bash will autostart on reboot

sudo systemctl status nginx

cat provision.sh - check what is in provision.sh

./provision.sh - run provision bash script 

#############################################################################

# Environmental Variables 

Environment variables - value stored in memory; accessbile for other tools in linux; all defined in caps 

printenv - print evironment variables

printenv USER - print USER variable from list 

echo "print" - show on screen

MYNAME = kevin (saved variable in linux but not environment variable)

echo $MYNAME - this will print kevin 

export MYNAME=kevin - make it an environment variable 

export MYCATSNAME=silkie - create env varibale straight 

configure to keep env varibales persistant after loggin in - edit file bash rc

nano .bashrc

CATSNAME=Bobby save and exit 

tail -5 .bashrc

source .bashrc - reload bashrc to environment variable 

printenv CATSNAME

exit and login and check again

ps - what processes is running in which terminal session 

bash what shell your running? command: ps -p $$

# PROCESSES in LINUX
there are two types of processes!

1. system processes ps -A, ps aux - this gives your more information all processes. system and user

2. user processes: ps command brings up user processes 

every process has a process id. (PID) something always has to start the process. parent process needs to start child process.


## Task 1.4.1 What is virtualisation?

# What is virtualisation?

The process of creating a virtual version of a computer Operating system or resources, such as hardware, operating systems, storage devices, or network resources. It allows multiple virtual machines or environments to run concurrently on a single physical computer or server.

types inc:
hardware, desktop, application, storage and network

What is a virtual machine?

A software emulation of a physical computer system. It is created within a virtualization environment and operates as a self-contained entity with its own virtualized hardware components, including a virtual CPU, memory, storage, and network interfaces.

# Where can they be run?

desktops 
servers 
cloud computing 
virtualization platforms
containerized environments 


# What determines how many can run?

VM can be run simultaneously but depends on various factos including physical resourceses, resource allocation, workload characteristics, hypervisor efficiency, VM configeration and adminstrative policies. Ensure capacity planning and performance testing to determin optimal number of VMs.


# What does a virtual machine include?


Virtual CPU. This virtual CPU emulates the behavior of a physical CPU and executes instructions within the virtual machine.

Memory: This memory is dedicated to the virtual machine and is used to run the operating system and applications within it.

Virtual Disks: Virtual machines have virtual disks that simulate physical hard drives or storage devices.

Virtual Network Interfaces: These interfaces allow the virtual machine to send and receive data over the network.

Operating System: A virtual machine runs its own operating system compatible with OS for example, linux

Virtual Hardware Drivers: hardware drivers to interact with the virtualized hardware components.


# What software is required to orchestrate/run the virtual machines?

Virtual machines require virtualization platforms and hypervisor software. Examples of some software include:

VMware vSphere
Microsoft Hyper-V
KVM (Kernel-based Virtual Machine)
Xen
Oracle VM VirtualBox

# What is the importance of an image when creating an VM?

reproducibility 
time saving 
consistency 
standarization
versioning and rollback 
security

# VM and Annotations 

![Alt text](<VM Diagram .png>)

