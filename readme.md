# Installation guide for ERPNEXT

## create new user and assign sudo permission to the new user crm

 sudo adduser crm

 sudo usermod -aG sudo crm

 sudo mkdir /home/crm/.ssh

 sudo cp ~/.ssh/authorized_keys /home/crm/.ssh/

 sudo chown -R crm:crm /home/crm/.ssh

 sudo chmod 700 /home/crm/.ssh

 sudo chmod 600 /home/crm/.ssh/authorized_keys


## Installation of System-wise dependencies
 sudo apt update

 sudo apt upgrade -y

 sudo apt update

 sudo apt install -y software-properties-common

 sudo add-apt-repository ppa:deadsnakes/ppa

 sudo apt update

 sudo apt install -y python3.10 python3.10-dev python3.10-venv build-essential redis-server mariadb-server mariadb-client libmysqlclient-dev xvfb libfontconfig    wkhtmltopdf git curl


 sudo mysql_secure_installation

curl -fsSL https://deb.nodesource.com/setup_18.x | sudo -E bash -

sudo apt install -y nodejs

sudo npm install -g yarn

sudo apt update

sudo apt install -y python3-mysqldb python3-dev

sudo apt install -y python3-pip



## CRM User
 su crm

 python3.10 -m venv env

 source /path/to/frappe-bench/env/bin/activate

 pip3 install frappe-bench

 npx update-browserslist-db@latest

 bench init frappe-bench --frappe-branch version-15


## Site Creation
bench new-site kgglcrm.com



## Install ERPNEXT 

bench get-app erpnext --branch version-15 https://github.com/frappe/erpnext.git

bench --site kgglcrm.com install-app erpnext



## Install PM2

sudo npm install -g pm2


