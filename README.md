Game Hosting [Open Source project] More..


MRV for Game Hosting [Open Source project]

[Website, Order, Online Payment, Game Panel, Admin Panel]


About us

uskoro bato, no sikiriki

Frontend: BlackQuard

Backend: o-net.me;

Ubuntu 18.04 +

Update & Upgrade!

sudo apt-get update -y
[web server]

sudo apt-get install -y apache2
sudo chmod -R 777 /var/www
[php]

sudo apt install software-properties-common
sudo add-apt-repository ppa:ondrej/php
sudo apt install -y php7.3
sudo apt-get install -y php-ssh2
enable [.htaccess]

	sudo a2enmod rewrite
	sudo systemctl restart apache2
	sudo nano /etc/apache2/apache2.conf
	---------------------------------------
	scroll to down:
		<Directory /var/www/> &
	replace this line:
		AllowOverride None |> AllowOverride All
[db server & phpmyadmin]

Database (MariaDB) & phpmyadmin:
	(https://www.digitalocean.com/community/tutorials/how-to-install-and-secure-phpmyadmin-on-ubuntu-20-04)
For fix problem "Not found" with phpmyadmin:
	(https://stackoverflow.com/a/46151947)
For problem with root login:
	(https://stackoverflow.com/a/52382478)
[proftpd]

sudo apt-get install -y proftpd
more settings:
	(https://mxforge.com/linux-windows/install-proftpd-with-tls-on-ubuntu-20-04-lts/)
zip, unzip, screen

sudo apt-get install -y zip, unzip, screen

Download gamepanel from github using this command line:

wget https://github.com/mrv-gamepanel/mrv.gp.open/archive/refs/heads/master.zip

[database config]

config file: /core/inc/config.php

[setup game dirvers]

https://linuxgsm.com/lgsm/sampserver/

CentOS 7+

[web server]

sudo yum install httpd
sudo chmod -R 777 /var/www
[php]

sudo install php
yum install https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm
yum install http://rpms.remirepo.net/enterprise/remi-release-7.rpm
yum install yum-utils
yum-config-manager --enable remi-php73
yum install php php-mcrypt php-cli php-gd php-curl php-mysql php-ldap php-zip php-fileinfo
[enable .htaccess]

sudo nano /etc/httpd/conf/httpd.conf

	<Directory /var/www/html>
		AllowOverride All
	</Directory>

sudo systemctl restart httpd
(https://tweenpath.net/enable-mod_rewrite-apache-centos-7/)

[php - ssh2 lib]

yum install gcc php-devel libssh2 libssh2-devel php-pear make
pecl install -f ssh2
echo extension=ssh2.so > /etc/php.d/ssh2.ini
service httpd restart
(https://www.svnlabs.com/blogs/install-ssh2-extension-for-php-7-on-centos-7/)

[--]

yum install -y screen, zip, unzip
[db server]

sudo yum install mariadb-server
sudo systemctl start mariadb.service
sudo mysql_secure_installation
[phpmyadmin]

sudo yum install phpmyadmin

You developer? Please fork and if found bugs fixed or report it. Thanks! <3














# SwiftPanel
         
         
         Install SwiftPanel on Centos
         yum install redhat-lsb
         wget https://raw.githubusercontent.com/zer0xpl0ide/Swift-Panel/master/install.sh
         chmod +x *
         ./install.sh
         
         Open DataBase
         mysql -u root -p  (Write you password)
         CREATE DATABASE zeropanel;
         CREATE USER 'zeropanel'@localhost IDENTIFIED BY 'gpanel1';
         GRANT ALL PRIVILEGES ON zeropanel.* TO 'zeropanel'@localhost;
         use zeropanel;
         exit
         
         Info DataBase
         hostname - localhost
         username - zeropanel
         name -     zeropanel
         password - gpanel1
         
         
        Add info to configuration.php
        And go youdomain.com/install
        And you finish install go /var/www/html and remove folder " install "
        Thanks you
        
Problem? : contact in fb.com/zer0xpl0ide
         
 
   To Install Swift Panel With Game In Root Follow The Steps

Step One—Install Apache

STEP 1 - sudo yum install httpd
STEP 2 - sudo service httpd start
Step Two—Install MySQL

STEP 1 - yum install mysql-server
STEP 2 - /sbin/chkconfig --levels 235 mysqld on
STEP 3 - service mysqld start
STEP 4 - mysql_secure_installation
STEP 5 - press ENTER
STEP 6 - Set Root Password(when it ask)
STEP 7 - Remove anonymous users?(when it ask) [Y/n] y
STEP 8 - Disallow root login remotely?(when it ask)[Y/n] n
STEP 9 - Remove test database and access to it?(when it ask) [Y/n] y
STEP 10 - Reload privilege tables now?(when it ask) [Y/n] y
STEP 11 - mysql -u root -p (then login with ur pw that u set)
STEP 12 - CREATE DATABASE gpanel;
STEP 13 - CREATE USER 'gpanel'@localhost IDENTIFIED BY 'gpanel1';
STEP 14 - GRANT ALL PRIVILEGES ON gpanel.* TO 'gpanel'@localhost;
STEP 15 - use gpanel;
STEP 16 - exit
Step Three—Install PHP

STEP 1 - yum install php
STEP 2 - yum search php
STEP 3 - yum install php-mysql php-gd php-imap php-ldap php-mbstring php-odbc php-pear php-xml php-xmlrpc
STEP 4 - yum install php-pecl-apc
STEP 5 - /etc/init.d/httpd restart
STEP 6 - service httpd restart
Step Four—Install Ioncube Loader

STEP 1 - wget -q -O - http://www.atomicorp.com/installers/atomic |sh
STEP 2 - yum install php-ioncube-loader
STEP 3 - service httpd restart
Step Five—Setup FTP Server

STEP 1 - yum install -y vsftpd
STEP 2 - service vsftpd start
STEP 3 - chkconfig vsftpd on
STEP 4 - vi /etc/vsftpd/vsftpd.conf (then a file will be opened in console so edit they following things :-

Press INSERT in your keyborad to start editing
anonymous_enable=NO
ascii_upload_enable=YES
ascii_download_enable=YES
use_localtime=YES(add this like at last)
Press ESC in ur keyboard to stop editing
Press [Shift+;] in ur keyborad then write "wq"[without ""] to save and exit

STEP 5 - service vsftpd restart
STEP 6 - chmod -R 777 /home
Step Six—Install SSH2

STEP 1 - yum install automake
STEP 2 - yum install php-devel
STEP 3 - yum install libtool
STEP 4 - yum install openssl-devel
STEP 5 - yum install gcc-c++
STEP 6 - cd /usr/src
STEP 7 - wget http://www.libssh2.org/download/libssh2-1.3.0.tar.gz
STEP 8 - tar -zxf libssh2-1.3.0.tar.gz
STEP 9 - cd libssh2-1.3.0
STEP 10 - yum install gcc php-devel php-pear libssh2 libssh2-devel
STEP 11 - ./configure
STEP 12 - make all install
STEP 13 - cd /usr/src
STEP 14 - rm -rf libssh2-1.3.0
STEP 15 - rm -rf libssh2-1.3.0.tar.gz
STEP 16 - cd /usr/lib64/php
STEP 17 - wget http://pecl.php.net/get/ssh2-0.11.3.tgz
STEP 18 - tar -zxf ssh2-0.11.3.tgz
STEP 19 - cd ssh2-0.11.3
STEP 20 - phpize && ./configure --with-ssh2 && make
STEP 21 - cd modules
STEP 22 - mv ssh2.so /usr/lib64/php/modules
STEP 23 - cd /usr/lib64/php
STEP 24 - rm -rf ssh2-0.11.3.tgz
STEP 25 - rm -rf ssh2-0.11.3
STEP 26 - touch /etc/php.d/ssh2.ini
STEP 27 - echo extension=ssh2.so > /etc/php.d/ssh2.ini
STEP 28 - /etc/init.d/httpd restart
STEP 29 - php -m | grep ssh2
Step Seven—Install CS 1.6 and CSCZ

STEP 1 - cd /root
STEP 2 - yum install vsftpd screen nano unzip ld-linux.so.2 -y
STEP 3 - mkdir -p /game/public
STEP 4 - rm -rf /game/public/*
STEP 5 - yum install glibc.i686 libstdc++.i686
STEP 6 - mkdir ~/steamcmd
STEP 7 - cd ~/steamcmd
STEP 8 - wget http://media.steampowered.com/installer/steamcmd_linux.tar.gz
STEP 9 - tar -xvzf steamcmd_linux.tar.gz
STEP 10 - rm -rf steamcmd_linux.tar.gz
STEP 11 - ./steamcmd.sh
STEP 12 - login anonymous
STEP 13 - force_install_dir /game/public
STEP 14 - app_update 90 beta validate
SETP 15 - app_update 90 validate
STEP 16 - app_set_config 90 mod czero
STEP 17 - app_update 90
STEP 18 - app_update 90
STEP 19 - app_update 90 -validate
STEP 20 - exit
STEP 21 - cd /game/public
STEP 22 - wget x-panel.tk/steampll.zip
STEP 23 - unzip steampll.zip
STEP 24 - rm -rf steampll.zip
STEP 25 - mv dproto.cfg /game/public/cstrike
STEP 26 - wget x-panel.tk/steamczpll.zip
STEP 27 - unzip steamczpll.zip
STEP 28 - rm -rf steamczpll.zip
STEP 29 - mv dproto.cfg /game/public/czero
STEP 30 - cd /root
STEP 31 - rm -rf steamcmd
STEP 32 - rm -rf Steam
Step Eight—Download and Setup Swift Panel

STEP 1 - cd /var/www/html
STEP 2 - wget x-panel.tk/swift.zip
STEP 3 - unzip swift.zip
STEP 4 - rm -rf swift.zip
STEP 5 - chmod -R 777 templates_c
STEP 6 - Now ur open root ip address with your browser with /install. eg. Open 5.231.37.188/install
STEP 7 - Follow the steps and at last it will show u admin Id and Password
STEP 8 - rm -rf install
STEP 9 - Now login Admin Account and open Manage Games
STEP 10 - Open Counter Strike 1.6
STEP 11 - Change Max Fps to 1024 and Pingboost to 2
STEP 12 - Change Install Directiry to /game/public and remove "-autoupdate" line from start command
STEP 13 - Now open Counter Strike-Condition Zero
STEP 14 - Change Max Fps to 1024 and Pingboost to 2 and map to de_dust2_cz
STEP 15 - Change Install Directiry to /game/public and remove "-autoupdate" line from start command
STEP 16 - Click and add Box with your root login details.    
         
         
         
        
