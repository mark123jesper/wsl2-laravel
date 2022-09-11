**Prepare setup to install PHP**
``` bash 
sudo add-apt-repository ppa:ondrej/php
```

**Update packages available**
``` bash
sudo apt-get update && sudo apt-get upgrade
```

**Install PHP 8**
``` bash
sudo apt-get install php8.0
```

**Install PHP Extensions, curl, mysql and more useful tools needed**
``` bash
sudo apt-get install jq xsel libnss3-tools zip unzip nginx mysql-server redis-server php8.0-fpm php8.0-cli php8.0-mysql php8.0-sqlite3 php8.0-intl php8.0-zip php8.0-xml php8.0-curl php8.0-mbstring php8.0-redis php-pear php8.0-dev php8.0-gd -y
```

**Installing Node Using the Node Version Manager**
``` bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.38.0/install.sh | bash
source ~/.bashrc
nvm install v14.15.1
```

**MySQL Setup:**
``` bash
sudo usermod -d /var/lib/mysql/ mysql
sudo service mysql start
sudo mysql
ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY '';
FLUSH PRIVILEGES;
exit
sudo service mysql restart
```

**Laravel Valet Setup**
<br>
Composer:
``` bash
cd ~
wget https://getcomposer.org/installer
php installer
sudo mv composer.phar /usr/local/bin/composer
```

Bash:
``` bash
nano ~/.bash_aliases
```
1. Put `export PATH=~/.config/composer/vendor/bin:$PATH`
2. Save the file, and then `source ~/.bashrc

Using Valet:
``` bash
composer global require cpriego/valet-linux
valet install
```

**Create Laravel app for testing**
``` bash
sudo chown -R your_user /opt/
cd /opt
composer create-project laravel/laravel example-app
cd example-app
valet link
sudo service nginx start
sudo service php8.0-fpm start
sudo service redis-server start
sudo service mysql start` // just making sure
```
1. Add `127.0.0.1 example-app.test` to your Windows HOST file
2. Navigate to `http://example-app.test to check


