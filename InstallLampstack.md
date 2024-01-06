Installing a  Lampstack
Ensure that your system has the latest information about available packages.
```
sudo apt update
```

Install the Apache web server.
```
sudo apt install apache2
```

Start and enable Apache to run on boot
```
sudo systemctl start apache2
sudo systemctl enable apache2
```

Install the MariaDB server.
```
sudo apt install mariadb-server
```

Start and enable MariaDB
```
sudo systemctl start mariadb
sudo systemctl enable mariadb
```

Install PHP and the required Apache module
```
sudo apt install php libapache2-mod-php php-mysql
```

Edit the Apache configuration to prioritize PHP files.
```
sudo nano /etc/apache2/mods-enabled/dir.conf
```

Move the PHP index file (index.php) to the beginning of the list. The file should look like this

Save the file and restart Apache
```
sudo systemctl restart apache2
```

Create a test PHP file in the Apache web server's document root.
```
echo "<?php phpinfo(); ?>" | sudo tee /var/www/html/info.php
```

Secure MariaDB Installation
```
sudo mysql_secure_installation
```


