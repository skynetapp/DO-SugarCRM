#### Date: 01-02-2017
#### Description: This document aims the installation of SugarCRM in DigitalOcean.

### Step 1:
  Login to the DigitalOcean with your email and password. Link: https://cloud.digitalocean.com/login
  
  ![login](https://cloud.githubusercontent.com/assets/22937653/22506035/4b15c88e-e8a4-11e6-83d5-c20b10862a85.PNG)
  
### Step 2:
  Create a droplet by clicking on the button which can be seen at the top right after login. The options are selected automatically, so we need to just click on the create button at the end.
  
  ![droplet](https://cloud.githubusercontent.com/assets/22937653/22507714/db6e21c6-e8ac-11e6-93f2-72d55389f029.PNG)
  ![create-droplet](https://cloud.githubusercontent.com/assets/22937653/22507743/f9c9794a-e8ac-11e6-8b30-527f50ccc8d5.PNG)
  
### Step 3:
  Here the droplet will be created with unique IP address and we will get a mail with the Droplet Name,IP address,username and password. 
  
  ![droplet-creating](https://cloud.githubusercontent.com/assets/22937653/22507807/3e93a4ec-e8ad-11e6-9296-4a096f2fe8ed.PNG)
  
### Step 4:
  Log into putty using the IP address.
  
  ![putty-login](https://cloud.githubusercontent.com/assets/22937653/22507830/545e09b6-e8ad-11e6-8aa1-770bc8ca312d.PNG)
  
### Step 5:
  Login as **root** and the password will be in the received mail id. click enter.
  
  ![putty-afterlogin](https://cloud.githubusercontent.com/assets/22937653/22507847/66a250aa-e8ad-11e6-8819-9297f828b5d6.PNG)
  
### Step 6:
  putty will be asking for the entered password and we can change the password for our droplet.
  
  ![password](https://cloud.githubusercontent.com/assets/22937653/22507986/01251400-e8ae-11e6-84c6-2639bff06f17.PNG)
  
### Step 7:
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
   - Now updating the package index by following command.
   
```
    sudo apt-get update
    
```

![inst1](https://cloud.githubusercontent.com/assets/22937653/22508092/79b3b55c-e8ae-11e6-8e28-254f80247d37.PNG)


   - Install the mysql server package which contains MYSQL version which is selected.
   
```
    sudo apt-get install mysql-server
    
```

![inst2](https://cloud.githubusercontent.com/assets/22937653/22508117/93107d5a-e8ae-11e6-9455-041b562f25d6.PNG)


   - Here we will be asking a password while installation which will be used later.
   
![installation-password](https://cloud.githubusercontent.com/assets/22937653/22508148/af67541a-e8ae-11e6-985f-850315bb203f.PNG)


   - Re-Enter the password again.
   
![repeat-password](https://cloud.githubusercontent.com/assets/22937653/22508160/c0473f7a-e8ae-11e6-93c3-4bd00e6f1ead.PNG)

   
   - For Configuring into MYSQL we need to setup the security process by following comand.
```
    sudo mysql_secure_installation
    
```

![installation](https://cloud.githubusercontent.com/assets/22937653/22508200/f3ade706-e8ae-11e6-8c2e-04bd653795d7.PNG)


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
   
![install](https://cloud.githubusercontent.com/assets/22937653/22508267/3b6d0b4e-e8af-11e6-8d24-3609be9d5ae8.PNG)
 
   - Are you Ready to install page will be seen. Click on Next.
   
![install1](https://cloud.githubusercontent.com/assets/22937653/22508306/63fa8b68-e8af-11e6-8906-aa08dc1f2cc9.PNG)

   - Click on **Accept** and proceed to Next.
   
![install2](https://cloud.githubusercontent.com/assets/22937653/22508374/a1d74692-e8af-11e6-94c6-617cc0f03a10.PNG)

   - It will ask for the installation options. select **Typical Install** and click on Next.
   
![install3](https://cloud.githubusercontent.com/assets/22937653/22508396/b821535c-e8af-11e6-8283-c0b11963c59c.PNG)

   - Database Type page can be seen which will be selected by default. Click on Next.
   
![install4](https://cloud.githubusercontent.com/assets/22937653/22508413/d12aa38a-e8af-11e6-997f-ce1b327b4248.PNG)

   - Database configuration page can be seen in which we need to enter the database name, host name as **localhost**, username as **root** and password.
   The password should be the same when you have done the initail setup for mysql. click on Next.
   
   
![install5](https://cloud.githubusercontent.com/assets/22937653/22508424/e418e3e4-e8af-11e6-95c8-f5cff0d5f493.PNG)

   - It will check the database and host and will proceed to Site Configuration page where we need to give the username and password details which will be used for login into sugar after the installation. Click on Next.
   
![usernamepassword](https://cloud.githubusercontent.com/assets/22937653/22508621/c791f354-e8b0-11e6-828e-fc4c2292d6f5.PNG)

   - Perform set up page will be displayed which tells us the sugar setup is completed.
   
![setup](https://cloud.githubusercontent.com/assets/22937653/22508735/34254b1a-e8b1-11e6-9ec2-dc7e2087e72a.PNG)

   - Here we will be asking to Install. click on **Install** button.
   
![final](https://cloud.githubusercontent.com/assets/22937653/22508449/0cfbce7a-e8b0-11e6-9357-737d6c797c18.PNG)

   - Login page can be seen, which we need to give the username and password which we have given at the time of Database configuration.

   - The Installation of sugar set up is completed.
   
   
   
    
  
  
  
