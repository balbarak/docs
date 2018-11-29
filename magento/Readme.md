
# Install Magento On Ubuntu Server 18 LTS
 
 In this you will find how to setup magento e-commerce platofrm on ubuntu server.


## Add repos and neccssory packages

* `sudo add-apt-repository ppa:ondrej/php`
* `sudo add-apt-repository universe`

## Install Apache2 and MySQL

* `sudo apt-get install unzip`
* `sudo apt-get install apache2`
* `sudo apt-get install mysql-server`

### Create magento dir and copy to files to it
* `sudo mkdir /var/www/html/magento`

### Set folder permission
* `sudo chown -R www-data:www-data /var/www/html/magento`
* `sudo chmod -R 755 /var/www/html/magento`


### Copy magento files to /var/wwww/html/magento
* `sudo unzip Magento.2.2.6.zip -d /var/wwww/html/magento`

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

### Check php version
* `php -v`


### Install mcrypt 
* `sudo apt-get install php-dev libmcrypt-dev gcc make autoconf libc-dev pkg-config`
* `sudo pecl install mcrypt-1.0.0`
