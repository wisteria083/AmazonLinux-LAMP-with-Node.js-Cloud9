# AmazonLinux-LAMP-with-Node.js-Cloud9

who -m

# ========================
# packages
# ========================
sudo yum -y install initscripts && sudo yum -y clean all && sudo yum -y update
sudo yum -y install gcc gcc-c++ make wget unzip git lm_sensors rpm-build yum-cron nfs-utils nfs-utils-lib nfs-common nap git glibc-static

# ========================
# nvm & node
# ========================
curl https://raw.githubusercontent.com/creationix/nvm/v0.30.1/install.sh | bash
source ~/.nvm/nvm.sh
nvm install 4.3.0
nvm alias default 4.3.0
nvm use default

sudo yum install -y httpd24
