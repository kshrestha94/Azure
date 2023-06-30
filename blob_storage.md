########################################################################## Reverse Proxy method:

1.sudo nano /etc/nginx/sites-available/default [nano into your default ]

2. "REPLACE" line: try_files $uri $uri/ =404; with proxy_pass http://localhost:3000; [relace http with new proxy pass]


3. sudo nginx -t [sudo nginx]


4. sudo systemctl restart nginx [restart nginx]

######################################################################### VM Script 
```
#!/bin/bash

# update
sudo apt update -y

# upgrade
sudo apt upgrade -y

# install nginx - when installed it starts autometically
sudo apt install nginx -y

# restart nginx
sudo systemctl restart nginx

# enable nginx - makes sure that when vm is restarted, ngix auto start on reboot
sudo systemctl enable nginx

# install nodejs
curl -sL https://deb.nodesource.com/setup_12.x | sudo -E bash -

# download nodejs
sudo apt install nodejs -y

# node package manager
sudo npm install pm2 -g

# copy app folder to VM
git clone https://github.com/jungjinggg/tech241_sparta_app.git app

# set env variable for the app to look up data from
export DB_HOST=mongodb://172.187.161.179:27017/posts

# go into the app folder
cd /home/adminuser/app/app

# install npm
npm install

# run sparta node app in the background
pm2 start app.j
```

############################################################################## DB VM script 
```
#!/bin/bash

# update
sudo apt update -y

# upgrade
sudo apt upgrade -y

# download key for the right version
wget -qO - https://www.mongodb.org/static/pgp/server-3.2.asc | sudo apt-key add -

# source list - specify mongo db version
echo "deb http://repo.mongodb.org/apt/ubuntu xenial/mongodb-org/3.2 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-3.2.list

# update again
sudo apt update -y

# install mongo db
sudo apt-get install -y mongodb-org=3.2.20 mongodb-org-server=3.2.20 mongodb-org-shell=3.2.20 mongodb-org-mongos=3.2.20 mongodb-org-tools=3.2.20

# configure bindip to 0.0.0.0
sudo sed -i 's/bindIp: 127.0.0.1/bindIp: 0.0.0.0/g' /etc/mongod.conf

# start mongo db
sudo systemctl restart mongod

# check the status
sudo systemctl status mongod

# enable mongo db
sudo systemctl enable mongod
```
############################################################################################### Blocker Resolved/ comments:
Whist creating a DB VM i chose the wrong Ubunto image preventing my script running.


################################################################ Blob storage ####################################################################################################################

Different ways to manipulate Blob storage
Azure CLI - command line interface  <--
Azure Portal 
Azure powershell 


############################### Daily Tasks! ###############################################################


# Blob storage Research task 1 #
```
a. what is it?
A cloud-based storage service that allows you to store and manage large amounts of unstructured data, such as text files, images, videos, audio files, backups, documents, and more. 
"blob" stands for Binary Large Object, 

b. difference between blob storage and the file system of Linux/Windows/Mac (hierachical file storage)

Azure Blob is an object storage solution. It allows you to store a large amount of unstructured data, whereas Azure files permit you to develop managed file share for the cloud. Azure file share can also be mounted by the on premises deployment of Windows, Linux, and macOS.

c. advantages/disadvantages of blob storage
Advantages:

1.store a large amount of unstructured data.
2.All the tires of the Blob are economical and give you the best value for your money.
3.Gives you the different storage classes for each category, additionally, it helps in categorizing the data.
4.Azure Blob provides 99.99999…% durability.
5.Backup options of the Blob are enticing.
6.Does not require the management of the operating system and hardware. With minimal management, it can replace an on premises server.
7.The automation of Blob is super easy and it is possible by using simple tools.

Disadvnatages :

1. The different storage plans could be costly for new users.
2. There is no automated backup for the Azure files.
3. One of the significant disadvantages is that it does not support direct attached storage. 

d. different tiers 

The Azure Blob has hot, cool, and archive tiers.

Hot – it has a low transactional cost but a high storage cost. And it is used for the frequent access of the object.
Archive – it has a higher transactional cost but a lower storage cost. The archive is the best option if you want long-term storage.
Cool – it is used to store the data that is accessed sporadically. The storage capacity of this tier is vast, and it can store data for 30 days. It has a low storage cost but high transactional expenses.

e. parts of Azure blob storage: account, container, blobs - how do they relate?

An Azure Blob Storage account serves as the top-level container for your storage resources.
Within an account, you can create one or more containers.
Each container acts as a logical grouping for related blobs.
Blobs are the individual data objects stored within containers, representing files or unstructured data.
```

# Research types of redundancy available with block blob storage task 2 #
```
Locally Redundant Storage (LRS): LRS stores multiple replicas of your data within a single data center. It provides durability and availability within that data center but does not replicate data to other data centers. LRS is the most cost-effective redundancy option.

Zone-Redundant Storage (ZRS): ZRS replicates your data across multiple data centers within a specific region. It provides higher durability and availability than LRS by storing replicas in separate physical locations within the same region. ZRS is suitable for scenarios that require higher resilience and data availability.

Geo-Redundant Storage (GRS): GRS provides replication of your data to a paired region, ensuring that data is stored in a separate region from the primary one. This redundancy option offers durability and availability across regions, protecting against regional disasters. In the event of an outage or disaster in the primary region, GRS allows failover to the secondary region.

Read-Access Geo-Redundant Storage (RA-GRS): RA-GRS provides the same replication as GRS but also allows read access to the data in the secondary region. This redundancy option enables read operations from the secondary region, making it useful for scenarios where data needs to be accessible for read purposes even during a primary region failure.

a. understand the difference between them

Choosing a redundancy option, consider your specific requirements for durability, availability, performance, and cost. Each redundancy level has its trade-offs in terms of cost and data accessibility in different failure scenarios.

Task 5.11: Adding an blob image to the Sparta test app
```

# CLI commands
```
az
az login - json returned login information - running through API

az storage account create --name tech241kevinstorage --resource-group tech241 --location uksouth --sku Standard_LRS

az storage account list --resource-group tech241

az storage account list --resource-group tech241 --query "[].{Name:name, Location:location, Kind:kind}" --output table

az storage container create --account-name tech241kevinstorage --name testcontainer

az storage blob upload \
 --account-name tech241kevinstorage \
 --container-name testcontainer \
 --name newname.txt \
 --file test.txt \
 --auth-mode login


az storage blob list \
 --account-name tech241kevinstorage \
 --container-name testcontainer \
 --output table \
 --auth-mode login

change privacy of containers - to blob only not private to access url


az storage blob upload --account-name tech241kevinstorage --container-name testcontainer --name catupload.jpg --file uploadedcat.jpg --auth-mode login

Modify the file index.ejs 
<img src="https://tech241kevinstorage.blob.core.windows.net/testcontainer/catupload.jpg" >
```

# sparta app with cat URL
 ```
http://20.58.21.167/
```