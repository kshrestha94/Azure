# Friday Sparta_app
## commands to install the app 
```
git clone https://github.com/jungjinggg/tech241_sparta_app.git (gitclone the sparta app using parichat github repo)
ls (check folder)
git clone https://github.com/jungjinggg/tech241_sparta_app.git sparta_aap_gitclone_method (change folder name)
ls
rm -rf tech241_sparta_app/ (delete tech241 sparta app)
ls
nano provision.sh (get it bash provision.sh script)

curl -sL https://deb.nodesource.com/setup_12.x | sudo -E bash -
sudo apt install nodejs -y (install node.js)
sudo npm install pm2 -g (install pm2)
ls
cd sparta_aap_gitclone_method/ (cd into your app directory)
cd app/ cd into the folder
npm install
ls
node app.js ( npm start check your sparta test app, paste your ip address add :3000 port. on azure network add 3000 port )

CtrlC or ^C to shut app off correctly 
ctrlZ or ^Z to shut app off but processes will keep running 

ps (user processes)
ps aux (system processes and all)

kill -1 3903 (weakest kill)
ps (check if termintated)
kill 3903 (try killing method)
ps
kill -9 3903 (brute force kill)
ps
npm start (start app again)
ls
```
## creating a new VM db 
```
Requirements to run DB VM:(DB terminal)
create a new VM for data base

1. linux VM -Ubuntu 18.04 LTS Gen2
ls
ls -a 

2. update and upgrade

sudo apt update -y
sudo apt upgrade -y
wget -qO - https://www.mongodb.org/static/pgp/server-3.2.asc | sudo apt-key add -
echo "deb http://repo.mongodb.org/apt/ubuntu xenial/mongodb-org/3.2 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-3.2.list

3. install mongo db version 3.2.x
 - download key for the right version (check key link from mongo bd)
 - source list - specify mongo.db version
 - update again
sudo apt update -y (update)
sudo apt-get install -y mongodb-org=3.2.20 mongodb-org-server=3.2.20 mongodb-org-shell=3.2.20 mongodb-org-mongos=3.2.20 mongodb-org-tools=3.2.20 (install)

4. configure mongo db to accept connections from app VM

sudo nano /etc/mongod.conf
bindIp: 0.0.0.0 for testing (adjustment for testing change bind IP)
cat /etc/mongod.conf (check for the changes made)

sudo systemctl status mongod (check status for mongo database - will appear dead)
sudo nano /etc/mongod.conf
sudo systemctl status mongod (check status)
sudo systemctl start mongod (start mongod)
sudo systemctl status mongod (enable mongod to run all the time)
```

## if post/connection to db set BD host (VM terminal)
```
ssh -i ~/.ssh/tech241-kevin-az-key adminuser@20.58.21.167 (ssh key from VM)
cd sparta_aap_gitclone_method/app/   (cd to correct folder path)
export DB_HOST=mongodb://172.187.179.8:27017/posts (export environment variable)
printenv DB_HOST (print evironment variable)
npm install 
npm start
open spart app url and insert /posts
```

