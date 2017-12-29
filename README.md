# Installation Laravel for Cloud 9
## Install PHP 7.1 and libs

sudo add-apt-repository ppa:ondrej/php

sudo apt-get update -y

sudo apt-get install -y php7.1 php7.1-zip php7.1-xml php7.1-mbstring php7.1-mysql 

sudo a2dismod php5 && sudo a2enmod php7.1 && sudo service apache2 restart

sudo composer self-update
## Update conf file

sudo vim /etc/apache2/sites-enabled/001-cloud9.conf

(replace DocumentRoot to /home/ubuntu/workspace/public)
## Update MYSQL
wget https://dev.mysql.com/get/mysql-apt-config_0.8.9-1_all.deb

sudo dpkg -i mysql-apt-config_0.3.3-1ubuntu14.04_all.deb

sudo apt-get update

sudo apt-get install mysql-server-5.7
## Create laravel project 
rm -rf * && rm -rf .*

composer create-project laravel/laravel ./laravel

shopt -s dotglob

mv laravel/* ./ && rm -rf laravel/
## Links
https://community.c9.io/t/getting-started-with-laravel/1608

https://stackoverflow.com/questions/45992685/php-parse-error-syntax-error-unexpected-in-helpers-php-233

https://serverfault.com/questions/752063/how-can-i-install-mysql-5-7-9-to-ubuntu-14-04
