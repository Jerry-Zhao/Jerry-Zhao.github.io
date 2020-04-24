---
layout: page
title: Help
permalink: /help/
--- 

# This is the help page for LongGeneDB.<br>
  <br>

**1. Install the LAMP Web Server.** <br>
**a. Install Apache 2** <br>
  Step 1: Update and Upgrade the apt tool to ensure we are working with the latest and greatest. <br>
         ***sudo apt update***  <br>
  Step 2: Install Apache and select Y when prompted. <br>
        ***sudo apt install apache2*** <br>
  Step 3:  Now that we have installed Apache we have to start the service. <br>
        ***systemctl start apache2*** <br>
  Step 4: Enabling Apache will automatically start the web server whenever the server is turned on. <br>
        ***systemctl enable apache2*** <br>
  Step 5: Verify Apache by visiting the server’shostname; you’ll see Apache’s default page. <br>
         ***https://localhost*** <br>
  Step 6: permissions to the /var/www/html folder <br>
        ***sudo gpasswd -a usnername www-data*** <br>
        ***sudo chown -R www-data:www-data /var/www/html*** <br>
        ***sudo chmod -R g+rwx /var/www/html*** <br>
  <br>
  <br>
**b. Install and Enable PHP**  <br>
  Step 1: install PHP <br>
     ***apt install php libapache2-mod-php php-mysql*** <br>
     ***php --version*** <br>
   Step 2: check that PHP is installed correctly <br>
     ***sudo vi /var/www/html/phpinfo.php***  <br>
     add ***\<?php phpinfo(); ?\>*** <br>
    change the permissions and ownership of the file <br>
    ***sudo chown www-data:www-data /var/www/html/phpinfo.php*** <br>
    ***sudo chmod +x /var/www/html/phpinfo.php*** <br>
    Open a web browser, enter ***http://localhost/phpinfo.php*** <br>
  <br>
  <br>
**c. Install MySQL**  <br>
   Step 1: Installing MySQL <br>
      ***sudo apt update*** <br>
      ***sudo apt install mysql-server*** <br>
   Step 2: Configuring MySQL <br>
      ***sudo mysql_secure_installation*** <br>
   Step 3: Adjusting User Authentication and Privileges <br>
      ***sudo mysql*** <br>
      ***SELECT user,authentication_string,plugin,host FROM mysql.user;*** <br>
      ***ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password';*** <br>
      ***FLUSH PRIVILEGES;***<br>
      ***SELECT user,authentication_string,plugin,host FROM mysql.user;***<br>
      ***exit***<br>
    <br>
    connect to MySQL with a dedicated user <br>
      ***mysql -u root -p*** <br>
      ***CREATE USER 'username##'@'localhost' IDENTIFIED BY 'password';*** <br>
      ***GRANT ALL PRIVILEGES ON *.* TO 'username##'@'localhost' WITH GRANT OPTION;*** <br>
      ***exit*** <br>
   Step 4: Testing MySQL <br>
    ***systemctl status mysql.service*** <br>
    ***sudo mysqladmin -p -u root version*** <br>
  <br>
  <br>
**d. install MySQL Workbench**  <br>
    ***sudo apt install mysql-workbench***<br>
  <br>
  <br>
**e. Install PHPMyAdmin**  <br>
  ***sudo apt install phpmyadmin***<br>
   <br>
  ***sudo ln -s /etc/phpmyadmin/apache.conf /etc/apache2/conf-available/phpmyadmin.conf***<br>
  ***sudo a2enconf phpmyadmin.conf***<br>
***sudo systemctl reload apache2.service***<br>
Test ***http://localhost/phpmyadmin***<br>
  <br>
  <br>
  **6.**  <br>
  <br>
  
  
