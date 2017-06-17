# aws_ec2_xamp
phpmyadmin connection in ec2 instance <br/>

ubuntu 16.04<br/>

Goto Terminal <br/>
sudo su<br/>
apt-get update<br/>
apt-get upgrade -y<br/>
apt-get dist-upgrade -y <br/>
apt-get autoremove -y<br/>

For Install PHP7.0 Mysql PhpMyAdmin & Apache 2<br/>
<br/>
apt-get install apache2 php7.0 php7.0-cli php7.0-fpm php7.0-gd libapache2-mod-php7.0 php7.0-mcrypt mysql-server php7.0-mysql git unzip zip postfix php7.0-curl mailutils php7.0-json phpmyadmin -y php7.0enmod mcrypt<br/>
<br/>
nano /etc/apache2/sites-enabled/000-default.conf<br/>
--ADD LINE-- <br/>
Include /etc/phpmyadmin/apache.conf<br/>
<br/>
service apache2 restart<br/>
<br/>
nano /etc/phpmyadmin/config.inc.php<br/>
--ADD LINES BELOW THE PMA CONFIG AREA AND FILL IN DETAILS--<br/>
$i++;<br/>
$cfg['Servers'][$i]['host']          = 'RDS Sever Path';<br/>
$cfg['Servers'][$i]['port']          = '3306';<br/>
$cfg['Servers'][$i]['socket']        = '';<br/>
$cfg['Servers'][$i]['connect_type']  = 'tcp';<br/>
$cfg['Servers'][$i]['extension']     = 'mysql';<br/>
$cfg['Servers'][$i]['compress']      = FALSE;<br/>
$cfg['Servers'][$i]['auth_type']     = 'config';<br/>
$cfg['Servers'][$i]['user']          = 'RDS User_Name';<br/>
$cfg['Servers'][$i]['password']      = 'RDS Password';<br/>



