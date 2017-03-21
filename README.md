# AmazonLinux-LAMP-with-Node.js-Cloud9

# packages
```text
sudo yum -y install initscripts && sudo yum -y clean all && sudo yum -y update  
sudo yum -y install gcc gcc-c++ make wget unzip git lm_sensors rpm-build yum-cron nfs-utils nfs-utils-lib nfs-common nap git glibc-static  
```

# git clone me
```text
git clone https://github.com/wisteria083/AmazonLinux-LAMP-with-Node.js-Cloud9.git ~/setup  
```

# nvm & node
```text
curl https://raw.githubusercontent.com/creationix/nvm/v0.30.1/install.sh | bash  
source ~/.nvm/nvm.sh  
nvm install 4.3.0  
nvm alias default 4.3.0  
nvm use default  
```

# apache
```text
sudo yum install -y httpd24  
sudo cp ./setup/httpd-*.conf /etc/httpd/conf.d/  
sudo cp ./setup/mod_*.conf /etc/httpd/conf.d/  

sudo sh -c "echo -e '  
Include conf.d/apache24-config/*.conf  
<Directory \"/var/www/html\">  
AllowOverride All  
</Directory>  
' >> /etc/httpd/conf/httpd.conf"  

chmod -R 777 /var/www/html

sudo service httpd start
sudo service httpd stop
```

# php 7.0
```text
sudo yum install -y php70 php70-common php70-devel php70-imap php70-mbstring php70-mcrypt php70-mysqlnd php70-pdo php70-xml

sudo sh -c "echo -e '
[PHP]
short_open_tag = On
[mbstring]
mbstring.language = Japanese
mbstring.internal_encoding = UTF-8
mbstring.http_input = UTF-8
mbstring.http_output = pass
mbstring.encoding_translation = Off
mbstring.detect_order = auto
mbstring.substitute_character = nones
' >> /etc/php.ini"

sudo service httpd start
sudo service httpd stop
```

# mysql5.6
```text
sudo yum install -y mysql56 mysql56-server
```

# redis
```text
sudo yum --enablerepo=epel install -y redis
```

# cloud9
```text
sudo yum install -y git gcc gcc-c++ openssl-devel readline-devel glibc-static
python -V

git clone git://github.com/c9/core.git ~/c9sdk
~/c9sdk/scripts/install-sdk.sh
npm install forever -g

mkdir -p /var/www/html/cloud9/workspaces/
forever start ~/c9sdk/server.js -w /var/www/html/cloud9/workspaces/ -p 8081 -a {user}:{password}
```

# apex
```text
curl https://raw.githubusercontent.com/apex/apex/master/install.sh | sudo sh
```
