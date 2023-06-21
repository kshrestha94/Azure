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
open GITBASH
copy chmod 400 

on notpad type: chmod 400 tech241-kevin-az-key

GITBASH 
paste: chmod 400 tech241-kevin-az-key
ls -l
check for rrr reas access tech241-kevin-az-key
ls

AZURE
private key path: ~/.ssh/tech241-kevin-az-key

part 4. run the example command below to connect to your VM
copy to clipboard

GITBASH 
paste; copy link from clipbaord above
ENTER
are you sure you want to connect? yes ENTER

ref:adminuser logged in
ls
ls -a (hidden folders)

VM started!!!!

to logout 
type: exit
then go back to AZURE 
overview STOP!
YES 




```
```python

Microsoft owned Azure basics – A cloud platform 
a huge collection of servers and networking hardware, which runs a complex set of distributed applications
Create VM Virtual Machine 
SSH into your VM – secure socket shell
Install Azure CLI
Create two Repositories – check video?

What is the cloud and what can you do with it?

Office – on premises 	Internet	Servers in Data center in region 1 – has its own cooling and power supply for backup. Eg.diesel generators	AWS
Home - local		Servers in Data center in region 2 – data centers are in different regions	
	The cloud – services and resources on the internet on demand 

Advantages of using the cloud 
•	Linked to external generators for back up  - back up infrastructure
•	Secure data 
•	Size of data center – economic scale buying in bulk is cheaper at peak times

Types of cloud:
Public cloud: for the general public; cloud storage to share, multi tenant 

Private cloud: single tenant cloud, dedicated by company (own private data center or hosted by third party. Does not have to be connected to internet. 

Hybrid cloud: mix of on premises and public cloud for resilience or disaster: back up
Multi cloud: using different cloud providers  



Shared responsibility – concepts 

•	IAAS (infrastructure as a service) service provider manages infrastructure. User has access to API and rents the infrastructure.
•	PAAS (platform as a service) – SQL service data base. Hardware and software platform provided and managed by cloud service provider. User manages the apps and the data the app replies on.
•	SAAS – (software as a service) you only need to manage data; don’t need to worry about managing other shared responsibilities. Service that delivers software application. SAAS are web applications or mobile apps. 

Using the cloud
Advantages 	Disadvantages 
Scalable on expansion of you need more computing resources; higher demand. 

Security 
Backup – power source 	Long response time possibly 
Less control in terms of management 

Hybrid or multi cloud
Advantages 	Disadvantages cloud
Mix of premises for resilience or protection from disaster 
Tailor to best service 	Complexity branches
Cost can be more expensive 
Security management 



On premises vs cloud. What is cheaper?
Cloud is cheaper because they can scale and buy servers in bulk. Cloud storage over hdd

Which cloud provider is best and why?
AWS – it has different types of cloud computing  - F1 runs data through aws


Presentation on cloud and advantage disadvantage

Microsoft Azure:
Monthly uptime percentage and service credit percentage you receive back – guarantee on service and what azure will compensate back as a percentage. 
Total cost of ownership TCO (on premises vs Cloud) 


Cloud providers market share top 3 
AWS
Azure – rising the most, Integration of services in one ecosystem
Google 

Smaller providers – difficult to get expertise engineers 
IBM, alibama 
Specialize in google and Microsoft to get paid more? More in demand 

 



What is Azure? How is it organized?
Tenant root group – active directory – entire setup
Root Management groups - help access policies and manage subs, managing specific size of virtual machine to reduce cost, ensure and enforce compliance, allow auditors to have permission to read only. 

Management groups can have sub management groups. 

Subscriptions – a way of separating payment account for bill, they have quotas, maximum of 980 resource groups. 

Pay as you go subscription eg -most popular. 
Limited Free subscription 

Resources groups - containers. Cannot have sub groups  
AWS does not have to use resource groups. Azure must have resource group. 


Resources: SQL etc 





What can we do with the cloud?

Manage and store data – processing data
Hosting software 
Computing resources 


 
 

Find your way around azure?
Create repository in GitHUB

Capital expenditure: large expenditure on premises – upfront cost – on premisis
Operational expenditure: cost spread out monthly – the cloud help with planning and budgeting. 

Tags: key pair to identify resources and billed grouped depending on the tag 
Team: sales team 1
Azure data storage into groups 

Pipeline: code gets pushed, checked, tested and delopyed -  pathway of automation
Azure category branch image:

```