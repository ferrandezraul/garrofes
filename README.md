About PrestaShop
--------

[![Build Status](https://travis-ci.com/PrestaShop/PrestaShop.svg?branch=develop)](https://travis-ci.com/PrestaShop/PrestaShop)
[![Gitter chat](https://badges.gitter.im/PrestaShop/PrestaShop.png)](https://gitter.im/PrestaShop/General)


PrestaShop is an Open Source e-commerce web application, committed to providing the best shopping cart experience for both merchants and customers. It is written in PHP, is highly customizable, supports all the major payment services, is translated in many languages and localized for many countries, has a fully responsive design (both front and back office), etc. [See all the available features][available-features].

<p align="center">
  <img src="https://user-images.githubusercontent.com/1009343/61462749-8fb19f00-a949-11e9-801f-70ab0a84192d.png" alt="PrestaShop 1.7 back office"/>
</p>

This repository contains the source code of PrestaShop, which is intended for development and preview only. To download the latest stable public version of PrestaShop (currently, version 1.7), please go to [the download page][download] on the official PrestaShop site.


About the 'develop' branch
--------

The 'develop' branch of this repository contains the work in progress source code for the next version of PrestaShop 1.7.
 
For more information on our branch system, read our guide on [installing PrestaShop for development][install-guide-dev].

The first stable version of PrestaShop 1.7, 1.7.0.0, was released on November 7th, 2016. Further updates have been released since then. Learn more about it on [the Build devblog](https://build.prestashop.com/tag/1.7/).

Server configuration
--------

To install the latest PrestaShop 1.7, you need a web server running PHP 7.1+ and any flavor of MySQL 5.0+ (MySQL, MariaDB, Percona Server, etc.). Versions between 1.7.0 and 1.7.6 work with PHP 5.6+.

You will also need a database administration tool, such as phpMyAdmin, in order to create a database for PrestaShop.
We recommend the Apache or Nginx web servers (check out our [example Nginx configuration file][example-nginx]).

You can find more information on our [System requirements][system-requirements] page and on the [System Administrator Guide][sysadmin-guide].

Installation
--------

If you downloaded the source code from GitHub, read our guide on [installing PrestaShop for development][install-guide-dev]. If you intend to install a production shop, make sure to download the latest version from [our download page][download], then read the [install guide for users][install-guide].

Docker compose
--------

PrestaShop can also be deployed with Docker and its tool [Docker compose][docker-compose].

To run the software, use:

```
docker-compose up
```

Then reach your shop on this URL: http://localhost:8001

Docker will bind your port 8001 to the web server. If you want to use other port, open and modify the file `docker-compose.yml`.
MySQL credentials can also be found and modified in this file if needed.

**Note:**  Before auto-installing PrestaShop, this container checks the file *config/settings.inc.php* does not exist on startup.
If you expect the container to (re)install your shop, remove this file if it exists. And make sure the container user `www-data` 
as write access to the whole workspace.

Documentation
--------

For technical information (core, module and theme development, performance...), head on to [PrestaShop DevDocs][devdocs]

If you want to learn how to use PrestaShop 1.7, read our [User documentation][user-doc].

First-time users will be particularly interested in the following guides:

* [Getting Started][getting-started]: How to install PrestaShop, and what you need to know.
* [User Guide][user-guide]: All there is to know to put PrestaShop to good use.
* [Updating Guide][updating-guide]: Switching to the newest version is not trivial. Make sure you do it right.
* [Merchant's Guide][merchant-guide]: Tips and tricks for first-time online sellers.
* The [FAQ][faq-17] and the [Troubleshooting][troubleshooting] pages should also be of tremendous help to you.


Contributing
--------

PrestaShop is an Open Source project, and it wouldn't be possible without the help of the [hundreds of contributors][contributors-md], who submitted improvements and bugfixes over the years. Thank you all!

If you want to contribute code to PrestaShop, read the [CONTRIBUTING.md][contributing-md] file in this repository or read the [tutorials about contribution][contributing-tutorial] on the documentation site.

If you want to help translate PrestaShop in your language, [join us on Crowdin][crowdin]!

Current Crowdin status (for 69 registered languages): [![Crowdin](https://crowdin.net/badges/prestashop-official/localized.png)](https://crowdin.net/project/prestashop-official)

Reporting Issues
--------

Our bugtracker is on GitHub. We encourage you to [create detailed issues][create-issue] as soon as you see them.

Read our [Contribute by reporting issues guide][reporting-issues] for details and tips.


Reporting Security Issues
--------

Responsible (and private) disclosure is a standard practice when someone encounters a security problem: before making it public, the discoverer informs the Core team about it, so that a fix can be prepared, and thus minimize the potential damage.

The PrestaShop team tries to be very proactive when preventing security problems. Even so, critical issues might surface without notice.

This is why we have set up the [security@prestashop.com](mailto:security@prestashop.com) email address: anyone can privately contact us with all the details about issues that affect the security of PrestaShop merchants or customers. Our security team will answer you, and discuss of a timeframe for your publication of the details.

Understanding a security issue means knowing how the attacker got in and hacked the site. If you have those details, then please do contact us privately about it (and please do not publish those details before we answer). If you do not know how the attacker got in, please ask for help on the support forums.


Extending PrestaShop
--------

PrestaShop is a very extensible e-commerce platform, both through modules and themes. Developers can even override the default components and behaviors. Learn more about this on the [Modules documentation][modules-devdocs] and the [Themes documentation][themes-devdocs].

Themes and modules can be obtained (and sold!) on [PrestaShop Addons][addons], the official marketplace for PrestaShop.


Community forums
--------

You can discuss about e-commerce, help other merchants and get help, and contribute to improving PrestaShop together with the PrestaShop community on [the PrestaShop forums][forums].

Thank you for downloading and using the PrestaShop Open Source e-commerce solution!

[available-features]: https://www.prestashop.com/en/online-store-builder
[download]: https://www.prestashop.com/en/download
[forums]: https://www.prestashop.com/forums/
[user-doc]: https://doc.prestashop.com
[contributing-md]: CONTRIBUTING.md
[contributing-tutorial]: https://devdocs.prestashop.com/1.7/contribute/
[crowdin]: https://crowdin.net/project/prestashop-official
[getting-started]: https://doc.prestashop.com/display/PS17/Getting+Started
[user-guide]: https://doc.prestashop.com/display/PS17/User+Guide
[updating-guide]: https://doc.prestashop.com/display/PS16/Updating+PrestaShop
[merchant-guide]: https://doc.prestashop.com/display/PS16/Merchant%27s+Guide
[faq-17]: https://build.prestashop.com/news/prestashop-1-7-faq/
[troubleshooting]: https://doc.prestashop.com/display/PS16/Troubleshooting
[sysadmin-guide]: https://doc.prestashop.com/display/PS16/System+Administrator+Guide
[addons]: https://addons.prestashop.com/
[contributors-md]: CONTRIBUTORS.md
[example-nginx]: docs/server_config/nginx.conf.dist
[docker-compose]: https://docs.docker.com/compose/
[install-guide-dev]: https://devdocs.prestashop.com/1.7/basics/installation/
[system-requirements]: https://devdocs.prestashop.com/1.7/basics/installation/system-requirements/
[install-guide]: https://doc.prestashop.com/display/PS17/Installing+PrestaShop
[devdocs]: https://devdocs.prestashop.com/
[create-issue]: https://github.com/PrestaShop/PrestaShop/issues/new/choose
[reporting-issues]: https://devdocs.prestashop.com/1.7/contribute/contribute-reporting-issues/
[modules-devdocs]: https://devdocs.prestashop.com/1.7/modules/
[themes-devdocs]: https://devdocs.prestashop.com/1.7/themes/


Raul's Notes
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