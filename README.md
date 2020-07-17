# Scope of Development 
---

#### Six Different types of Web Application 
1. Static Web Application 
2. Dynamic Web Application    
3. Online Store and E-Commerce 
4. Portal Web Application 
5. Animated Web Application
6. web Application with Content Management System

##### How many project at markertpalce ...

    1. Somethings 
    2. Somethings

* *Enterprise Resouce planning*
* *Human Resource Management System*
* *Sales Management System*
* *Hospital Management Information system* 
* *Eloctronic Medical Record* 
* *Radiology Information System* 
* *Picture Archiving & Communication System* 
* *Laboratory Infomation system* 
* *Training Management system* 
* *University Management System* 
* *Mediacal college Management System* 
* *Smart Home Solutions*
* *Vat Management System*
* *Ecommerece* 
* *Payment Gateway*
* *Api integration*
* *Digital Wallet*
* *Digital Bangking Application* 
* *Network Management System*
* *School Management System*
* *Trafic Management System*
* *Push Notication*
* *Messaging System*
* *Online Payment*
* *Blogging System*
* *Peronal Website*
* *Photo Management System*
* *Employee Monitoring System*
* *Tracking System*
* *SMS & Email System*
* *HR & Payroll System*
* *Banking Management System*
* *News Portal System*
* *Queue Management*
* *Integration with other System*
* *Testing System*
* *Photographer System*
* *Doctor Manage Appoinment Global*
* *Smart Health Monitoring & information System*
* *Survey System*
* *Domain Hosting System*

***

##### LAMP For Web Application delveloper 

###### for laravel 5.8 and and all other extension shortcut command 

* * sudo apt-get install php7.2 php7.2-common libapache2-mod-php7.2 php7.2-pear php7.2-mcrypt php7.2-curl php7.2-dev php7.2-gd php7.2-mbstring php7.2-zip php7.2-mysql php7.2-xml php-token-stream php7.2-cli php7.2-json *

#### PHP Version Upgrade

[Install or Upgrade to PHP 7.X on Ubuntu](https://techbrij.com/php-7-ubuntu-install-upgrade)
[left join in multiple tables](https://www.codeproject.com/Questions/693539/left-join-in-multiple-tables)


#### For Sql 

[sql query learning](https://gist.github.com/janikvonrotz/6e27788f662fcdbba3fb)

### command for linux 
* *:screenshot --fullpage info.png*


# Vertual Host for Ubuntu lamp user


#### Step One
Use this line Terminal
        
	 sudo mkdir -p /var/www/html/example.com/public_html
	
#### Step Two
Use this line Terminal

    sudo chown -R $USER:$USER /var/www/html/example.com/public_html

#### Step Three
 Use this line Terminal for full permission

    sudo chmod -R 755 /var/www/html


#### Step Four
 Use this line Terminal for demo page

    nano /var/www/html/example.com/public_html/index.html
    
    * example 
        <html>
          <head>
                <title>Welcome to Example.com!</title>
          </head>
        <body>
             <h1>Success!  The example.com virtual host is working!</h1>
         </body>
        </html>

#### Step Five
 Use this line Terminal virtual host file / cp means copy 

    sudo cp /etc/apache2/sites-available/000-default.conf /etc/apache2/sites-available/example.com.conf
###### open host file 
        sudo nano /etc/apache2/sites-available/example.com.conf
###### Paste host file and change your own sites serveradmin, servername,serveralias and documentroot must be added
        <VirtualHost *:80>
            ServerAdmin admin@example.com 
            ServerName example.com
            ServerAlias www.example.com
            DocumentRoot /var/www/example.com/public_html
            ErrorLog ${APACHE_LOG_DIR}/error.log
            CustomLog ${APACHE_LOG_DIR}/access.log combined
        </VirtualHost>
#### Step Six
Use this line Terminal for enable new virtual file

    sudo a2ensite example.com.conf
#### Step Seven
Use this line Terminal for apache2 restart

    sudo service apache2 restart
#### Step Eight
Use this line Terminal for local hosts file

     sudo nano /etc/hosts
###### use as like below 
        127.0.0.1   localhost
        127.0.1.1   guest-desktop
        127.0.0.2  example.com
## Test Result 
        http://example.com

    
### Others
বালুকাবেলায় সাইকেল বালিকা 
বালির রাজত্বে তোমার পদ চারণ
=====================================
for word press -> 
added config.php below ....  

define( 'UPLOADS', 'wp-content/uploads' );

last line added -> 
 define('FS_METHOD', 'direct');
......................................................................
sudo chmod -R 777 /var/www/html/sweety/wp-content/
======================================
sudo  find /var/www -type d -exec chmod 755 {} \;
sudo  find /var/www -type f -exec chmod 644 {} \;
==================================================

my new site http://sazzadbinashique.ashiknahid.com/

username : Mou20v1m7F
password : 3JtKBFPN@//m

==========================================
php artisan make:model Category -mcr


### Need for Ubuntu 

### Google analytics measurement on your site 
https://developers.google.com/analytics/devguides/collection/gtagjs



### Input any number in Bengali and the following function will return the English number.

function bn2enNumber ($number){
    $search_array= array("১", "২", "৩", "৪", "৫", "৬", "৭", "৮", "৯", "০");
    $replace_array= array("1", "2", "3", "4", "5", "6", "7", "8", "9", "0");
    $en_number = str_replace($search_array, $replace_array, $number);

    return $en_number;
}




