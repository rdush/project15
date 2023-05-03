### CONFIGURATION FOR NGINX AMI

`yum install -y https://dl.fedoraproject.org/pub/epel/epel-release-latest-8.noarch.rpm`

`yum install -y dnf-utils http://rpms.remirepo.net/enterprise/remi-release-8.rpm`

`yum install wget vim python3 telnet htop git mysql net-tools chrony -y`

`systemctl start chronyd`

`systemctl enable chronyd`

# Configure selinux policies for the nginx

`setsebool -P httpd_can_network_connect=1`

`setsebool -P httpd_can_network_connect_db=1`

`setsebool -P httpd_execmem=1`

`setsebool -P httpd_use_nfs 1`

# Instll amazon efs utils for mounting the target on the Elastic file system

`git clone https://github.com/aws/efs-utils`

`cd efs-utils`

`yum install -y make`

`yum install -y rpm-build`

`make rpm `

`yum install -y  ./build/amazon-efs-utils*rpm`

# seting up self-signed certificate for the nginx instance

`sudo mkdir /etc/ssl/private`

`sudo chmod 700 /etc/ssl/private`

`sudo openssl dhparam -out /etc/ssl/certs/dhparam.pem 2048`