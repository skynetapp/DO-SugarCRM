#### Date: 01-02-2017
#### Description: This document aims the installation of SugarCRM in DigitalOcean.

#### Step 1:
  Login to the DigitalOcean with your email and password. Link: https://cloud.digitalocean.com/login
  
  ![login](https://cloud.githubusercontent.com/assets/22937653/22506035/4b15c88e-e8a4-11e6-83d5-c20b10862a85.PNG)
  
#### Step 2:
  Create a droplet by clicking on the butto which can be seen at the top right. The options are selected automatically, so we need to just click on the create button at the end.
  
#### Step 3:
  Here the droplet will be created with unique IP address and we will get a mail with the Droplet Name,IP address,username and password. 
  
#### Step 4:
  Log into putty using the IP address.
  
#### Step 5:
  Login as **root** and the password will be in the received mail id. click enter.
  
#### Step 6:
  putty will be asking for the entered password and we can change the password for our droplet.
  
#### Step 7:
  First we need to install MySQL into our server by following below steps.
      
    - First we need to add a new APT Package from https://dev.mysql.com/downloads/repo/apt/. 
    - Click **Download** from bottom right and copy the link on the next page from **No thanks, start my download**.
    
```
    wget http://dev.mysql.com/get/mysql-apt-config_0.6.0-1_all.deb
    
```
   - Next Install it using dpkg.
   
```
    sudo dpkg -i mysql-apt-config_0.6.0-1_all.deb
    
```
   - Here we can prompt the MySQL version which we want to use. selet the version and click ok.
   - Now updating the package index by folowing command.
   
```
    sudo apt-get update
    
```
   - Install the mysql server package which contains MYSQL version which is selected.
   
```
    sudo apt-get install mysql-server
    
```
   - Here we will be asking a password while installation which will be used later.
   - For Configuring into MYSQL we need to setup the security process by following comand.
```
    sudo mysql_secure_installation
    
```
   - Here we will be asked some of the questions which we can  simply press Enter.
   - Now to check the MYSQL version the following command will be used.
```
    mysql --version
    
```
   - To check whether the MYSQL server is running or not, the following command is used.
```
    service mysql status
    
```
   - To test the mysql commands, the following command is used.
   
```
    mysql -u root -p
    
```  
   - This will ask the password which we have given at the time of installing the server and then we can execute the queries.
   - The installation of MySQL is completed.
   
#### Step 8
   Now we need to install the SugarCRM into our server using putty.
   
   - Download the latest version of SugarCRM Community Edition by folowing command.
   
```
    wget http://sourceforge.net/projects/sugarcrm/files/latest/download -O SugarCE-6.5.20.zip
    
```

   - Extract the zip folder and move the files to /var/www/html/sugar folder by following commands. 
   
```
    unzip SugarCE-6.5.20.zip
    mv SugarCE-Full-6.5.20 /var/www/html/sugar
    
```
   - Open the browser and run the IP Address followed by the folder name. we can see the sugar installation initial set up page. Click on Next.
   - Are you Ready to install page will be seen. Click on Next.
   - Click on **Accept** and proceed to Next.
   - It will ask for the installation options. select **Typical Install** and click on Next.
   - Database Type page can be seen which will be selected by default. Click on Next.
   - Database configuration page can be seen in which we need to enter the database name, host name as **localhost**, username as **root** and password.
   The password should be the same when you have done the initail setup for mysql. click on Next.
   - Here we will be asking to Install. click on **Install** button.
   - Login page can be seen, which we need to give the username and password which we have given at the time of Database configuration.
   - The Installation of sugar set up is completed.
   
   
   
    
  
  
  
