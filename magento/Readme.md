
# Install Magento On Ubuntu Server 18 LTS
 
 In this you will find how to setup magento e-commerce platofrm on ubuntu server.


## Add repos and neccssory packages

* `sudo add-apt-repository ppa:ondrej/php`
* `sudo add-apt-repository universe`

## Install Apache2 and MySQL

* `sudo apt-get install unzip`
* `sudo apt-get install apache2`
* `sudo apt-get install mysql-server`

### Create magento dir
* `sudo mkdir /var/www/html/magento`

### Copy magento files to /var/wwww/html/magento
* `sudo unzip Magento.2.2.6.zip -d /var/wwww/html/magento`


### Set folder permissions
* `sudo chown -R www-data:www-data /var/www/html/magento`
* `sudo chmod -R 755 /var/www/html/magento`


## Install php version 7.1 and its modules
* `sudo apt-get install php7.1`
* `sudo apt-get install php7.1-common`
* `sudo apt-get install php7.1-mbstring`
* `sudo apt-get install php7.1-xmlrpc` 
* `sudo apt-get install php7.1-soap`
* `sudo apt-get install php7.1-gd`
* `sudo apt-get install php7.1-xml`
* `sudo apt-get install php7.1-intl` 
* `sudo apt-get install php7.1-mysql`
* `sudo apt-get install php7.1-cli`
* `sudo apt-get install php7.1-ldap`
* `sudo apt-get install php7.1-curl`
* `sudo apt-get install php7.1-bcmath`
* `sudo apt-get install php7.1-mcrypt`
* `sudo apt-get install php7.1-zip`

### Setup Share file (optional)
This step is to share folder between windows and ubuntu

* `sudo apt-get install cifs-utils`
* `sudo mkdir /home/share`
* `sudo mount.cifs //10.1.1.2/Opensources /home/share -o user=Admin`

### Setup apache2 web server

Open apache2 config
* `sudo nano /etc/apache2/apache2.conf`

#### Replace 

```shell
<Directory /var/www/>
        Options Indexes FollowSymLinks
        AllowOverride none
        Require all granted
</Directory>
```

#### With 
``` shell
<Directory /var/www/>
        Options Indexes FollowSymLinks
        AllowOverride All
        Require all granted
</Directory>
```



### Setup MySql Database
* `sudo mysql`
* `CREATE DATABASE magento;`

Change `your_user` with your user and `you_pass` with your password

Note this grant will have no restrict in IP and it is not recommended for production

* `GRANT ALL ON magento.* TO 'your_user'@'%' IDENTIFIED BY 'you_pass' WITH GRANT OPTION;`


## Complete
Run your browser with `http://localhost/magento` if you install it on localmachine and follow the instructions
