INSTALLASI SELESAI

-----------------------------

apt update && upgrade -y
apt install net-tools
apt install vsftpd

------------------------------

INSTALLASI WEBSERVER (Apache2)

sudo apt install apache2
systemctl status apache2

------------------------------

PENGUJIAN WEBSERVER DI BROWSER

http://ip-server-anda

-------------------------------

INSTALL PHP Version 8

sudo apt install -y php php-{common,mysql,xml,xmlrpc,curl,gd,imagick,cli,dev,imap,mbstring,opcache,soap,zip,intl}
php -v

--------------------------------

INSTALL MariaDB or MySQL

sudo apt install mariadb-server mariadb-client -y
sudo systemctl enable --now mariadb
systemctl status mariadb

---------------------------------

SECURE YOUR DATABASE Installation

mysql_secure_installation

dialog :

Enter current password for root (enter for none): Press ENTER
Set root password? [Y/n]: Y
New password: masukan-password-root
Re-enter new password: masukan-password-root
Remove anonymous users? [Y/n] Y
Disallow root login remotely? [Y/n] Y
Remove test database and access to it? [Y/n] Y
Reload privilege tables now? [Y/n] Y

---------------------------------

MEMBUAT DATABASE UNTUK WORDPRESS

mysql -u root -p
CREATE USER 'wordpress'@'localhost' IDENTIFIED BY 'wordpress123';
CREATE DATABASE wordpress_db;
GRANT ALL PRIVILEGES ON wordpress_db.* TO 'wordpress'@'localhost';
FLUSH PRIVILEGES;
Exit;

----------------------------------

INSTALL WORDPRESS di Ubuntu 22.04

apt install wget unzip -y
wget https://wordpress.org/latest.zip
unzip latest.zip
mv wordpress/ /var/www/html/
rm latest.zip
chown www-data:www-data -R /var/www/html/wordpress/
chmod -R 755 /var/www/html/wordpress/

-----------------------------------

KONFIGURASI Apache / Webserver di Ubuntu 22.04

cd /etc/apache2/sites-available/
ls
cp 000-default.conf wordpress.conf
a2ensite wordpress.conf
a2enmod rewrite
a2dissite 000-default.conf
systemctl restart apache2

-----------------------------------

BUKA BROWSER UNTUK LANGKAH-LANGKAH SETUP WORDPRESS

http://ip-server-anda/wordpress
wordpress_db
wordpress
wordpress123
localhost
wp_

SMK Tinta Emas Indonesia
admin
@admin2023#
emailmu@gmail.com