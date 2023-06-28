# Wednesday 28/06/2023

## Tasks completed:
```
####### Automation L1 - Start the Sparta app with a script (no database) ############

understanding problem running app in background with &:
Answer: issue with immutable process PID and the sparta application will keep running.It is difficult to kill these process as they return once you exit the terminal. 
method to restart and kill process: switch off virtual machine and turn on again 

sparta test application script automation continued 

ps (user processes)
ps pux (print all processes)
ps aux | grep node (grab specific key word you are looking for)
jobs (check actice jobs that are running)
sudo kill 21377 (if process is running root privaliges to kill)
```
####### Automation L2 - Configure Mongo DB VM (including bindIp) with a script #########
```
Ensure you run the script on your DB Virtual Machine and then export your DB Host

For DB virtual machine:
chmod u+x provision_db.sh (give permissions)
./provision_db.sh 
```

Commands for VM:
```
export DB_HOST=mongodb://172.187.179.8:27017/posts
insert SSH KEY
cd sparta_aap_gitclone_method/app/
export DB_HOST=mongodb://172.187.179.8:27017/posts
printenv DB_HOST
npm install
npm start

sucessfully running sparta application by pasting url/posts
```
##################### Automation L3 - Modify app VM script to use database VM ######################
```
Virtual Machine created
Database Virtual MAchine created 

VM:
sparta application running 

VM Blocker:
sudo apt-get install -y mongodb-org=3.2.20 mongodb-org-server=3.2.20 mongodb-org-shell=3.2.20 mongodb-org-mongos=3.2.20 mongodb-org-tools=3.2.20 (package of mongodb installation error)
```