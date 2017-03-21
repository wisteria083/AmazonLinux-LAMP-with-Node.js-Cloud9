# AmazonLinux-LAMP-with-Node.js-Cloud9

# packages
sudo yum -y install initscripts && sudo yum -y clean all && sudo yum -y update
sudo yum -y install gcc gcc-c++ make wget unzip git lm_sensors rpm-build yum-cron nfs-utils nfs-utils-lib nfs-common nap git glibc-static

# git clone me
git clone git@github.com:wisteria083/AmazonLinux-LAMP-with-Node.js-Cloud9.git ~/setup

# nvm & node
curl https://raw.githubusercontent.com/creationix/nvm/v0.30.1/install.sh | bash
source ~/.nvm/nvm.sh
nvm install 4.3.0
nvm alias default 4.3.0
nvm use default

# apache
sudo yum install -y httpd24
sudo cp ./setup/httpd-*.conf /etc/httpd/conf.d/
sudo cp ./setup/mod_*.conf /etc/httpd/conf.d/
sudo sh -c "echo -e '
Include conf.d/apache24-config/*.conf
<Directory \"/var/www/html\">
AllowOverride All
</Directory>
' >> /etc/httpd/conf/httpd.conf"
