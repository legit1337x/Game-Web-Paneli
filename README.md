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
         
        
         
         
         
        
