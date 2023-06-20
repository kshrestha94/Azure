##Gitbash command to create VM
-----------------------------------------------------------------------------
```python


cd
pwd (present working directory)
mkdir .ssh  (folder to store keys; .is important to keep hidden)
cd .ssh
pwd
/c/Users/k.shrestha/.ssh (this is what should be printed)
ssh-keygen -t rsa -b 4096 -C "shrishrestha@hotmail.com"  (generate ssh key pair command)
tech241-kevin-az-key
enter enter -----
ls (you can see all keys in folder) .pub is the public key 
cat tech241-kevin-az-key
------copy long string into azure---- 

---------------------------------------------------------------------------------------

Azure:

search tab: ssh key 
create 
resource group: tech241
key pair name: tech241-kevin-az-key 
shh key source: upload existing 
upload key:------copy long string into azure---- 

tags options
name: owner tag 
value:kevin 
click:review and create 
create 

search:virtual machine (ok) if your not using VM STOP it!
create: azure virtual machine 
resource group: tech241
virtual machine name: tech241-kevin-man-app
region uk south
avail op: no infrastructure
security:standard 
image: Uburto pro 18.04 LTS
size: standard B1s (price unavailable)
auth type: ssh public key 
username: adminuser
ssh public key source: using existing key stored in azure 
stored keys: tech241-kevin-az-key

inbound port rules------------------------
select inbount ports: select http and ssh selected

disks
os disk type: standard ssd

tags 
name:owner
value:kevin 
  ---- click review  and create 
create (creates your VM)

click ----go to resource
overview 
click connect shh

chmod 400 tech241-kevin-az-key

```