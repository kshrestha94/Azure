# To start the Sparta app in a script on VM :3000 - 

# provision.sh
```
#!/bin/bash

# update -ensure source list is upto date
sudo apt update -y

# upgrade -install lastest package in linux; there are situations where upgrade isnt  req
sudo apt upgrade -y

# install nginx (sudo systemctl status nginx - to check - ctl z to come out and enter)
sudo apt install nginx -y

# restart nginx
sudo systemctl restart nginx

# enable nginx - when VM start/stops bash will autostart on reboot
sudo systemctl enable nginx

# install node.js (correct version)
curl -sL https://deb.nodesource.com/setup_12.x | sudo -E bash -
sudo apt install nodejs -y
#sudo npm install pm2 -g

# copy application folder to Virtual Machine
git clone https://github.com/jungjinggg/tech241_sparta_app.git

# Run Sparta Test app
cd sparta_aap_gitclone_method/app/
npm install -y
node app.js
```


# db provision_db.sh script

```
#!/bin/bash
## apt update and upgrade

sudo apt update -y
sudo apt upgrade -y
wget -qO - https://www.mongodb.org/static/pgp/server-3.2.asc | sudo apt-key add -
echo "deb http://repo.mongodb.org/apt/ubuntu xenial/mongodb-org/3.2 multiverse" | sudo tee /etc/apt/sou$


## install the correct version of Mongo DB
install mongo db version 3.2.x
sudo apt update -y
sudo apt-get install -y mongodb-org=3.2.20 mongodb-org-server=3.2.20 mongodb-org-shell=3.2.20 mongodb-o$

## configure mongo db to accept connections from app VM

sudo nano /etc/mongod.conf
cat /etc/mongod.conf

sudo systemctl status mongod
sudo nano /etc/mongod.conf
sudo systemctl status mongod

#start and enable
sudo systemctl start mongod
sudo systemctl status mongod

export DB_HOST=mongodb://172.187.179.8:27017/posts
ssh -i ~/.ssh/tech241-kevin-az-key adminuser@20.58.21.167
cd sparta_aap_gitclone_method/app/
export DB_HOST=mongodb://172.187.179.8:27017/posts
printenv DB_HOST
npm install
npm start
```
