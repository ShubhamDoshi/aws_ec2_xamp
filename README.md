# aws_ec2_xamp
phpmyadmin connection in ec2 instance

ubuntu 16.04

Goto Terminal 
sudo su
apt-get update
apt-get upgrade -y
apt-get dist-upgrade -y 
apt-get autoremove -y

For Install PHP7.0 Mysql PhpMyAdmin & Apache 2
apt-get install apache2 php7.0 php7.0-cli php7.0-fpm php7.0-gd libapache2-mod-php7.0 php7.0-mcrypt mysql-server php7.0-mysql git unzip zip postfix php7.0-curl mailutils php7.0-json phpmyadmin -y php7.0enmod mcrypt

nano /etc/apache2/sites-enabled/000-default.conf
--ADD LINE-- 
Include /etc/phpmyadmin/apache.conf

service apache2 restart

nano /etc/phpmyadmin/config.inc.php
--ADD LINES BELOW THE PMA CONFIG AREA AND FILL IN DETAILS--
$i++;
$cfg['Servers'][$i]['host']          = 'RDS Sever Path';
$cfg['Servers'][$i]['port']          = '3306';
$cfg['Servers'][$i]['socket']        = '';
$cfg['Servers'][$i]['connect_type']  = 'tcp';
$cfg['Servers'][$i]['extension']     = 'mysql';
$cfg['Servers'][$i]['compress']      = FALSE;
$cfg['Servers'][$i]['auth_type']     = 'config';
$cfg['Servers'][$i]['user']          = 'RDS User_Name';
$cfg['Servers'][$i]['password']      = 'RDS Password';



