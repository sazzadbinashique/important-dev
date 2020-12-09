# Scope of Development 

---

## Laravel
#### laravel crud command (m=migration, c=controller r=resource)
```
php artisan make:model Category -mcr
```
---
## Important Function for work 

#### Input any number in Bengali and the following function will return the English number.
```php
function bn2enNumber ($number){
    $search_array= array("১", "২", "৩", "৪", "৫", "৬", "৭", "৮", "৯", "০");
    $replace_array= array("1", "2", "3", "4", "5", "6", "7", "8", "9", "0");
    $en_number = str_replace($search_array, $replace_array, $number);

    return $en_number;
}
```
#### youtube link convert as embed link 
```php
function convertYoutube($url) {
        return preg_replace(
            "/\s*[a-zA-Z\/\/:\.]*youtu(be.com\/watch\?v=|.be\/)([a-zA-Z0-9\-_]+)([a-zA-Z0-9\/\*\-\_\?\&\;\%\=\.]*)/i",
            "https://www.youtube.com/embed/$2", $url
        );
   }
  ```
####  PHP Random unique code generate 
```php
 function randdomCode($length = 8) {
        $characters = '0123456789abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ';
        $charactersLength = strlen($characters);
        $randomString = '';
        for ($i = 0; $i < $length; $i++) {
            $randomString .= $characters[rand(0, $charactersLength - 1)];
        }
        return $randomString;
    }
```
#### PHP Function for user IP Address 

```php
function getUserIpAddr() {
        if (!empty($_SERVER['HTTP_CLIENT_IP'])) {
            //ip from share internet
            $ip = $_SERVER['HTTP_CLIENT_IP'];
        } elseif (!empty($_SERVER['HTTP_X_FORWARDED_FOR'])) {
            //ip pass from proxy
            $ip = $_SERVER['HTTP_X_FORWARDED_FOR'];
        } else {
            $ip = $_SERVER['REMOTE_ADDR'];
        }
        return $ip;
    }
```
#### PHP Function For Browser info  
```php
function getBrowserWithVersion() {
        $u_agent = isset($_SERVER['HTTP_USER_AGENT']) ? $_SERVER['HTTP_USER_AGENT'] : '';
        $browser = 'Unknown';
        $platform = 'Unknown';
        $version = " ";
        $ref = isset($_SERVER['HTTP_REFERER']) ? $_SERVER['HTTP_REFERER'] : '';
        $os_array = array(
            '/windows nt 10/i' => 'Windows 10',
            '/windows nt 6.3/i' => 'Windows 8.1',
            '/windows nt 6.2/i' => 'Windows 8',
            '/windows nt 6.1/i' => 'Windows 7',
            '/windows nt 6.0/i' => 'Windows Vista',
            '/windows nt 5.2/i' => 'Windows Server 2003/XP x64',
            '/windows nt 5.1/i' => 'Windows XP',
            '/windows xp/i' => 'Windows XP',
            '/windows nt 5.0/i' => 'Windows 2000',
            '/windows me/i' => 'Windows ME',
            '/win98/i' => 'Windows 98',
            '/win95/i' => 'Windows 95',
            '/win16/i' => 'Windows 3.11',
            '/macintosh|mac os x/i' => 'Mac OS X',
            '/mac_powerpc/i' => 'Mac OS 9',
            '/linux/i' => 'Linux',
            '/ubuntu/i' => 'Ubuntu',
            '/iphone/i' => 'iPhone',
            '/ipod/i' => 'iPod',
            '/ipad/i' => 'iPad',
            '/android/i' => 'Android',
            '/blackberry/i' => 'BlackBerry',
            '/webos/i' => 'Mobile'
        );

        foreach ($os_array as $regex => $value) {
            if (preg_match($regex, $u_agent)) {
                $platform = $value;
            }
        }

        // Next get the name of the useragent yes seperately and for good reason
        if (preg_match('/MSIE/i', $u_agent) && !preg_match('/Opera/i', $u_agent)) {
            $browser = 'Internet Explorer';
            $ub = "MSIE";
        } elseif (preg_match('/Firefox/i', $u_agent)) {
            $browser = 'Mozilla Firefox';
            $ub = "Firefox";
        } elseif (preg_match('/OPR/i', $u_agent)) {
            $browser = 'Opera';
            $ub = "Opera";
        } elseif (preg_match('/Chrome/i', $u_agent) && !preg_match('/Edge/i', $u_agent)) {
            $browser = 'Google Chrome';
            $ub = "Chrome";
        } elseif (preg_match('/Safari/i', $u_agent) && !preg_match('/Edge/i', $u_agent)) {
            $browser = 'Apple Safari';
            $ub = "Safari";
        } elseif (preg_match('/Netscape/i', $u_agent)) {
            $browser = 'Netscape';
            $ub = "Netscape";
        } elseif (preg_match('/Edge/i', $u_agent)) {
            $browser = 'Edge';
            $ub = "Edge";
        } elseif (preg_match('/Trident/i', $u_agent)) {
            $browser = 'Internet Explorer';
            $ub = "MSIE";
        } else {
            $ub = "Unknown";
        }

        // finally get the correct version number
        $known = array('Version', $ub, 'other');
        $pattern = '#(?<browser>' . join('|', $known) .
                ')[/ ]+(?<version>[0-9.|a-zA-Z.]*)#';
        if (!preg_match_all($pattern, $u_agent, $matches)) {
            // we have no matching number just continue
        }

        // see how many we have
        $i = count($matches['browser']);
        if ($i != 1) {
            //we will have two since we are not using 'other' argument yet
            //see if version is before or after the name
            if (strripos($u_agent, "Version") < strripos($u_agent, $ub)) {
                $version = $matches['version'][0];
            } else if(isset($matches['version'][1])) {
                $version = $matches['version'][1];
            } else {
                $version = 'n/a';
            }
        } else {
            $version = $matches['version'][0];
        }

        // check if we have a number
        if ($version == null || $version == "") {
            $version = "?";
        }

        return array(
            'userAgent' => $u_agent,
            'browser' => $browser,
            'version' => $version,
            'platform' => $platform,
            'ref' => $ref
        );
    }

```

---

### LAMP For Web Application delveloper 

##### for laravel 5.8 and and all other extension shortcut command 

* * sudo apt-get install php7.2 php7.2-common libapache2-mod-php7.2 php7.2-pear php7.2-mcrypt php7.2-curl php7.2-dev php7.2-gd php7.2-mbstring php7.2-zip php7.2-mysql php7.2-xml php-token-stream php7.2-cli php7.2-json *

### PHP Version Upgrade

* [Install or Upgrade to PHP 7.X on Ubuntu](https://techbrij.com/php-7-ubuntu-install-upgrade)

---

#### For Sql 

* [sql query learning](https://gist.github.com/janikvonrotz/6e27788f662fcdbba3fb)
* [left join in multiple tables](https://www.codeproject.com/Questions/693539/left-join-in-multiple-tables)
---

### command for linux
  Full Page screenShot  on console

```full page
 :screenshot --fullpage info.png*
```

---

## Vertual Host for Ubuntu lamp user

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

---
    
## For wordpress 
added config.php below ...  
```
define( 'UPLOADS', 'wp-content/uploads' );
```
last line added ... 
```
define('FS_METHOD', 'direct');
```

```
sudo chmod -R 777 /var/www/html/sweety/wp-content/
```
---

### directory and file permision chaged command 
```
sudo  find /var/www -type d -exec chmod 755 {} \;
sudo  find /var/www -type f -exec chmod 644 {} \;
```
---
### Google analytics measurement on your site 
+ [Google Analytics](https://developers.google.com/analytics/devguides/collection/gtagjs)

---

## We Needed As Developer Webisite  

---
<table>
<thead>
<tr>
 <th>Template Free </th>
 <th>Admin Template</th>
 <th>Blog Website</th>
 <th>Social Website</th>
 <th>Photography Website</th>
</tr>
</thead>
<tbody>
 <tr>
 <td><a href="">AdminLite</a></td>
 <td><a href="">AdminLite</a></td>
 <td><a href="">AdminLite</a></td>
 <td><a href="">AdminLite</a></td>
 <td><a href="">AdminLite</a></td>
</tr>
</tbody>
</table>

* *Enterprise Resource planning*

***




