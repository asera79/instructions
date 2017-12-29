# Installation Laravel for Cloud 9
## Install PHP 7.1 and libs
sudo add-apt-repository ppa:ondrej/php
sudo apt-get update -y
sudo apt-get install -y php7.1 php7.1-zip php7.1-xml php7.1-mbstring php7.1-sqlite3 
sudo a2dismod php5 && sudo a2enmod php7.1 && sudo service apache2 restart
sudo composer self-update
## Update conf file
sudo vim /etc/apache2/sites-enabled/001-cloud9.conf
(replace DocumentRoot to /home/ubuntu/workspace/public)
## Create laravel project 
rm -rf * && rm -rf .*
composer create-project laravel/laravel ./laravel
shopt -s dotglob
mv laravel/* ./ && rm -rf laravel/
## Links
https://community.c9.io/t/getting-started-with-laravel/1608
https://stackoverflow.com/questions/45992685/php-parse-error-syntax-error-unexpected-in-helpers-php-233
