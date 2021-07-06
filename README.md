About PrestaShop
--------

[![Build Status](https://travis-ci.com/PrestaShop/PrestaShop.svg?branch=develop)](https://travis-ci.com/PrestaShop/PrestaShop)
[![Gitter chat](https://badges.gitter.im/PrestaShop/PrestaShop.png)](https://gitter.im/PrestaShop/General)


PrestaShop is an Open Source e-commerce web application, committed to providing the best shopping cart experience for both merchants and customers. It is written in PHP, is highly customizable, supports all the major payment services, is translated in many languages and localized for many countries, has a fully responsive design (both front and back office), etc. [See all the available features][available-features].

<p align="center">
  <img src="https://user-images.githubusercontent.com/1009343/61462749-8fb19f00-a949-11e9-801f-70ab0a84192d.png" alt="PrestaShop 1.7 back office"/>
</p>

This repository contains the source code of PrestaShop, which is intended for development and preview only. To download the latest stable public version of PrestaShop (currently, version 1.7), please go to [the download page][download] on the official PrestaShop site.

Notes
--------

Note the prestashop - PHP version compatibility!
For prestashop 1.7, php 7.4 does not work. Use php 7.3 instead.
This repo uses prestashop 1.7.7.5 and php 7.3.

```
In case you have php7.4 and php 7.3, you can switch php versions. This shows switching from 7.4 to 7.3:

sudo a2dismod php7.4

sudo a2enmod php7.3

sudo service apache2 restart
   

sudo update-alternatives --set php /usr/bin/php7.3

sudo update-alternatives --set phar /usr/bin/phar7.3

sudo update-alternatives --set phar.phar /usr/bin/phar.phar7.3

sudo update-alternatives --set phpize /usr/bin/phpize7.3

sudo update-alternatives --set php-config /usr/bin/php-config7.3

```

Create database:
```
sudo mysql -u root -p
CREATE DATABASE prestashop COLLATE utf8mb4_general_ci;
CREATE USER "prestashopuser"@"hostname" IDENTIFIED BY "somepassword";
GRANT ALL PRIVILEGES ON prestashop.* TO "prestashopuser"@"hostname";
```

Be sure the auth mechanism is mysql_native_password. Check it with:
```
SELECT User, Host, plugin FROM mysql.user;
```
Otherwise, enter mysql and change it:
```
sudo mysql -u root -p
ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'my_password';
```

In your debian, install dependencies:
```
sudo apt install apache2 libapache2-mod-php mysql-server 
sudo apt install libapache2-mod-php7.3 php7.3 php7.3-common php7.3-curl php7.3-gd php7.3-imagick php7.3-mbstring php7.3-mysql php7.3-json php7.3-xsl php7.3-intl php7.3-zip
```

Clone the prestashop git repo and checkout the desired version:
```
https://github.com/PrestaShop/PrestaShop/tree/1.7.8.x

git checkout 1.7.7.5
```

Install composer (php dependency manager):
```
php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"

php -r "if (hash_file('sha384', 'composer-setup.php') === '756890a4488ce9024fc62c56153228907f1545c228516cbf63f885e036d37e9a59d27d63f46af1d4d07ee0f76181c7d3') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"

php composer-setup.ph

php composer.phar update

sudo mv composer.phar /usr/local/bin/composer

composer --version

composer install
```

Set up appropiate permissions:
```
chmod +w -R admin-dev/autoupgrade app/config app/logs app/Resources/translations cache config download img log mails modules themes translations upload var
```

Then, start the installation of prestashop by entering the following command in your prestashop root folder:
```
php -S localhost:8000
```

Load CSV data
--------

In the admin panel (localhost/['ADMIN_FOLDER_NAME']), go to "Advanced settings", "Import" and load csv files in this order:

/docs/csv_import/garrofes/categories_import.csv
/docs/csv_import/garrofes/suppliers_import.csv
/docs/csv_import/garrofes/customers_import.csv
/docs/csv_import/garrofes/addresses_import.csv

### Errors

If you are using MySQL 8.0 and observe that your application is experiencing error related caching_sha2_password plugin, it is likely because your clients/connectors does not (yet) support caching_sha2_password plugin. 


To resolve this issue, you may consider using mysql_native_password as default authentication for MySQL 8.0 server. 


Add following entry in MySQL configuration file. (/etc/mysql/my.cnf)
```
[mysqld]
default-authentication-plugin=mysql_native_password
```
Then `sudo service mysql restart`


If running the server fails due to php errors, try to get your php dependencies again:
```
rm -rf vendor/prestashop
rm -rf vendor/*
```

If you get an error on ContextErrorException in ImageRetriever.php, run the following sql statement in phpmyadmin:
```sql
INSERT INTO `ps_image_type` (`id_image_type`, `name`, `width`, `height`, `products`, `categories`, `manufacturers`, `suppliers`, `stores`)
VALUES
	(10, 'large_banner', 960, 400, 0, 1, 0, 0, 0),
	(9, 'product_listing', 220, 220, 1, 1, 1, 1, 0),
	(8, 'category_default', 960, 350, 0, 1, 0, 0, 0),
	(7, 'home_default', 250, 250, 1, 0, 0, 0, 0),
	(6, 'large_default', 500, 500, 1, 0, 0, 0, 0),
	(5, 'medium_default', 300, 300, 1, 1, 1, 1, 0),
	(4, 'small_default', 125, 125, 1, 1, 1, 1, 0),
	(3, 'cart_default', 80, 80, 1, 0, 0, 0, 0);

```
If you can not access the phpmyadmin:
```
sudo mysql --user=root mysql
CREATE USER 'phpmyadmin'@'localhost' IDENTIFIED BY '<please_replace_this>';
GRANT ALL PRIVILEGES ON *.* TO 'phpmyadmin'@'localhost' WITH GRANT OPTION;
FLUSH PRIVILEGES;
```

If you can not access the phpmyadmin with user root, it might be due to the auth mechanism set to auth_socket.
Check output from:
```
SELECT User, Host, plugin FROM mysql.user;
```

and then run:
```
ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'thepassword';
```


## TODO
Menu de arriba con arbol de Categorias y Proveedores
Simplificar footer aun mas.
Product atribute para el pan cortado y demas atributos
Mirar algun addon o theme
Eliminar imagen no disponible trasteando en los archivos del theme (si no el theme peta) o usando otro theme.
Desplegar en heroku.
