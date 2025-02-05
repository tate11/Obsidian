[[AWS EC2]]
see also [[Git]]
see also [[SSH]]
AS Ubuntu
```ubuntu
sudo apt-get update
sudo apt-get upgrade
sudo adduser odoo --home /home/odoo --shell /bin/bash
sudo usermod -aG sudo odoo
sudo nano /etc/ssh/sshd_config
sudo cp -r /home/ubuntu/.ssh /home/odoo/
sudo chown -R odoo:odoo /home/odoo/.ssh
sudo chmod 700 /home/odoo/.ssh
sudo service ssh restart
```

Then Login into

```odoo
sudo apt install -y postgresql
sudo pg_lsclusters
sudo su root
su postgres
psql -p 5432 -U postgres -d postgres 
CREATE USER odoo PASSWORD 'xxx';"
ALTER USER odoo WITH SUPERUSER;"
\q  or Ctrl+d
exit
exit
```

alter security group rule open port
```odoo
sudo apt install build-essential wget git python3-pip python3-dev python3-venv python3-wheel libfreetype6-dev libxml2-dev libzip-dev libsasl2-dev python3-setuptools libjpeg-dev zlib1g-dev libpq-dev libxslt1-dev libldap2-dev libtiff5-dev libopenjp2-7-dev
```

```odoo
sudo apt install -y npm
sudo apt install -y node-less
sudo npm install -g less less-plugin-clean-css
mkdir /home/odoo/Documents
mkdir /home/odoo/Downloads
cd /home/odoo/Downloads
sudo wget https://github.com/wkhtmltopdf/wkhtmltopdf/releases/download/0.12.5/wkhtmltox_0.12.5-1.bionic_amd64.deb
sudo apt install ./wkhtmltox_0.12.5-1.bionic_amd64.deb -y
mkdir /home/odoo/Documents/Github
sudo mkdir /var/log/odoo
sudo chown odoo:root /var/log/odoo
sudo apt install python3-pip
```

```postgresql
pg_dump  -p 5432 -d mydb -F c -f /home/odoo/mydb.dump
createdb -p 5434 -U odoo mydb
pg_restore -p 5434 -d mydb mydb.dump
```

```github
mkdir /home/odoo/Documents/Github/odoo
cd /home/odoo/Documents/Github/odoo/
git clone https://www.github.com/odoo/odoo --depth 1 --branch 16.0
cd /home/odoo/Documents/Github/odoo/odoo
pip3 install -r requirements.txt
```

```direct
wget -q -O - https://nightly.odoo.com/odoo.key | sudo gpg --dearmor -o /usr/share/keyrings/odoo-archive-keyring.gpg

 echo 'deb [signed-by=/usr/share/keyrings/odoo-archive-keyring.gpg] https://nightly.odoo.com/16.0/nightly/deb/ ./' | sudo tee /etc/apt/sources.list.d/odoo.list
 
sudo apt-get update && sudo apt-get install odoo
```

```odoo
sudo service odoo stop
edit config file
tail -f -n 100 /var/log/odoo/odoo-server.log
```
