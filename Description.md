# Creating Database MYSQL, Web Server Apache2 and Content by PHP to enable a server to host dynamic websites and web apps. 

### step 1:

In Linux (kali) operating system make sure its an updated or upgraded version, If not,

> sudo apt update 

Then move to 

##### installation of Apache2 Web server.

Check for Apache2 if not then install using below command.
>sudo apt install apache2

We can check status using below command 
>sudo service apache2 status

we can restart by using below command if already install but its status is Dead.
>sudo service apache2 start


We can now check our web browser to verify our server’s public IP address working fine or not.

To check public IP address go to terminal and give command as

>sudo ifconfig

Take public IP and paste in our web browser,

In your browser in URL

>http://your server IP 

example :

>http://127.0.0.1

Screen shot 



### step 2

##### installation of MYSQL

Check for MYSQL if not then install using below command.
>sudo apt install mysql-server

We can check status using below command 
>sudo service mysql status

we can restart by using below command if already install but its status is Dead.
>sudo service mysql start

### step 3

##### installation of PHP

In default we have php installed in Kali Linux, but check for the latest version and update it

>sudo apt-install python3

To check the version of 
>php -v

### step 4

##### Configuration of Apache with local directory or website Directory.

Create a website directory
>sudo mkdir sudo mkdir /var/www/html/ phone (Domain name) 

>sudo chmod -R 777 /var/www/html/phone (Domain name)

>copy requried files like php,html and database to estabilish or to run webpage in browser from 

https://github.com/harish2830/phone.git

### step 5

##### Create a new virtual host configuration.

Go to the path below 
>cd /etc/apache2/sites-available

list out for above path we can see below files
>ls
000-default.conf  default-ssl.conf 

We need to create a host file for configuration

>cp 000-default.conf phone.com.conf

>sudo vim phone.com.conf

<VirtualHost *:80>

     Servername phone.com(Domain.com)
     ServerAdmin webmaster@localhost
     DocumentRoot /var/www/html/phone (/var/www/html/Domainname)

     <Directory /var/www/html/domainname/public>
         Options Indexes FollowSymLinks
         AllowOverride All
         Require all granted
     </Directory>

     ErrorLog ${APACHE_LOG_DIR}/error.log 
     CustomLog ${APACHE_LOG_DIR}/access.log combined 
 </VirtualHost>

 >sudo /etc/hosts

 >127.0.0.1 localhost phone.com (Domainname.com)
 127.0.1.1 kali

Enable the new configuration.

>sudo a2ensite phone.com(Domainname.com)

System control reload by Apache2

>sudo systemctl reload apache2

![]{} check 


### step 















