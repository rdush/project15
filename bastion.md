### bation configuration

`yum install -y https://dl.fedoraproject.org/pub/epel/epel-release-latest-8.noarch.rp`

`yum install -y dnf-utils http://rpms.remirepo.net/enterprise/remi-release-8.rpm`

`yum install wget vim python3 telnet htop git mysql net-tools chrony -y`

`systemctl start chronyd `

`systemctl enable chronyd`

# 
`mysql -h acs-database.cfgqfrt0xivm.us-east-1.rds.amazonaws.com -u ACSadmin -p`

` mysql> create Database wordpressdb; `

`mysql> create database toolingdb; `