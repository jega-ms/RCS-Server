# RCS-Server Setup


## Step 1    
Update the system and install the necessary dependencies
	
```
	apt update 
	apt install mysql-server 
```
## Step 2 
Install the kamailio and kamailio modules 

```	
	apt install kamailio kamailio-mysql-modules
	apt install kamailio* (all modules 
```
## Step 3 

Enable RCS releated modules e.g Auth, Presence Server, Mysql and debug 

Open the file ` vi /etc/kamailio/kamailio-local.cfg  ` and add the below modules. t 

pre-processor for corresponding module

```
	#!define WITH_DEBUG 
	#!define WITH_MYSQL 
	#!define WITH_AUTH 
	#!define WITH_USRLOCDB
```


## Step 4

Enable XCAP Server Module 

Follow the instruction for config module 

[https://www.kamailio.org/docs/modules/5.1.x/modules/xcap_server.html] (https://www.kamailio.org/docs/modules/5.1.x/modules/xcap_server.html) 
 
## Step 5

Enable MSRP Module 

Follow the instruction for config module and enable the pre-processor in step2 

[https://www.kamailio.org/docs/modules/5.1.x/modules/msrp.html]()


## Step 6 
Run the below command to verify the kamailio configuration. 

```
kamalio -c 

```

## Step 7

Setup the database and user credentials 

To create the MySQL database, you have to use the database setup script. First edit kamctlrc file to set the database server type

```
vi /etc/kamailio/kamctlrc  
``` 
update ` "DBENGINE=MYSQL" `


## Step 8 

A new account can be added using kamctl tool via:

```
# kamctl add username password email
```



