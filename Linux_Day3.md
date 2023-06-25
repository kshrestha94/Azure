# Linux d3.markdown

## public IP address (associated with VM)
```
- static IP (keeps it the same; default on Azure used for production VM) less security 
- dynamics IP (default on AWS on every restart of VM)
```

## processes continued 
```
ps - terminal processes 
ps aux - all processes 
```

## commands continued 
```
sleep 3 - sleep for 5 seconds handy to wait for script run 
sleep 5000 & - sleep for 5000 seconds and prints processor id
jobs - check jobs list 
jobs --help - check the jobs help tool
jobs -l - check running and process id 
```
## terminating processes: 
```
sometimes app might be running and you need to kill the app because it is already running 
kill -1 (process id) this will kill sleep; check using jobs -gentle way of killing 
kill (process id) forcefull kill terminate 
kill -15 (process id)
kill -9 (brute force kill; important one) this will kill parent process however will keep child zombie processes

parent process will create and branch chid processes (if we used kill -15 - this will kill all child processes and then kill parent process)

ps -ef ( command that will show parent process id )

control system processes 
sudo systemctl start nginx
sudo systemctl stop nginx
sudo systemctl status nginx

```
## sparta test app - deploy (works in port 3000)
```
- node js app - javascript framework 
- works in port 3000
- 2 features 
     1. front web page, no data base needed
     2. post page retrieves information from data base

- bash script to run sparta app 
```
## Requirements to run sparta application 
```
1. Linux VM version ubuntu 18.04 LTS
2. web server - nginx 
3. right version of node js - version 12.x works fine (dependency all installments and config for data base to run)
4. app folder
5. inn app folder run two commands: 
      1. npm install 
      2. node app.js OR npm start 

Get the 'app' folder onto the Azure VM

unzip and extract files to folder. 

git clone method
1. create git repo -tech241-sparta-app
2. create folder "tech241-sparta-app" on your local machine 
3. copy app folder to locak repo
4. syc with your remote repo on github
5. SSH in to VM and git clone 

SCP or rsync

1. you will need private key 
2. path to folder
3. adminuser@<IP-address-vm>

ssh in and check it worked

```
