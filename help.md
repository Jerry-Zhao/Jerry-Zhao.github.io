---
layout: page
title: Help
permalink: /help/
--- 

# This is the help page for LongGeneDB.<br>
  <br>

  **1. Install the LAMP Web Server.** <br>
 **a. Install Apache 2** <br>
  Step 1: Update and Upgrade the apt tool to ensure we are working with the latest and greatest.
         ***sudo apt update***  
  Step 2: Install Apache and select Y when prompted.
        ***sudo apt install apache2***
  Step 3:  Now that we have installed Apache we have to start the service.
        ***systemctl start apache2*** 
  Step 4: Enabling Apache will automatically start the web server whenever the server is turned on.
        ***systemctl enable apache2***
  Step 5: Verify Apache by visiting the server’shostname; you’ll see Apache’s default page.
         ***https://localhost***
  <br>
  **b. Install and Enable PHP**  <br>
     ***apt install php libapache2-mod-php php-mysql***
     ***php --version***
  <br>
  **c. Install MySQL**  <br>
   Step 1: Installing MySQL
      ***sudo apt update    ***
      ***sudo apt install mysql-server   *** 
    Step 2: Configuring MySQL
      ***sudo mysql_secure_installation ***
 
    Step 3: Adjusting User Authentication and Privileges
    sudo mysql
    SELECT user,authentication_string,plugin,host FROM mysql.user;
    ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password';
    FLUSH PRIVILEGES;
    SELECT user,authentication_string,plugin,host FROM mysql.user;
    exit
    
    connect to MySQL with a dedicated user
    mysql -u root -p
    CREATE USER 'username##'@'localhost' IDENTIFIED BY 'password';
    GRANT ALL PRIVILEGES ON *.* TO 'username##'@'localhost' WITH GRANT OPTION;
    exit
    Step 4: Testing MySQL
    systemctl status mysql.service
    sudo mysqladmin -p -u root version
    
  <br>
  **4.**  <br>
  <br>
  **5.**  <br>
  <br>
  **6.**  <br>
  <br>
  
  
