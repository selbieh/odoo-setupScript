# odoo-setupScript


sudo -i 



STEP 1
sudo apt-get update
STEP 2
sudo apt-get -y upgrade
STEP 3
sudo apt-get install python3-pip python3-setuptools libpq-dev python3-dev build-essential libssl-dev libffi-dev


INSTALL DEPENDENCIES USING PIP3
sudo pip3 install -U pyyaml==3.13 





sudo pip3 install wheel psycopg2-binary psycopg2==2.7.1 Babel decorator paramiko docutils ebaysdk feedparser gevent greenlet html2text Jinja2 lxml Mako MarkupSafe mock num2words ofxparse passlib Pillow psutil psycogreen pydot pyparsing PyPDF2 pyserial python-dateutil python-openid pytz pyusb  qrcode reportlab requests six suds-jurko vatnumber vobject Werkzeug XlsxWriter xlwt xlrd phonenumbers


STEP 4
sudo apt-get install -y npm
sudo ln -s /usr/bin/nodejs /usr/bin/node
sudo npm install -g less less-plugin-clean-css
sudo apt-get install node-less


STEP 5
install gedit from mint https://community.linuxmint.com/software/view/gedit

sudo apt-get install python-software-properties

sudo gedit /etc/apt/sources.list.d/pgdg.list


add a line for the repository


deb http://apt.postgresql.org/pub/repos/apt/ xenial-pgdg main


wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | sudo apt-key add -
sudo apt-get update
sudo apt-get install postgresql-9.6
STEP 6
Create Database user for Odoo
sudo su postgres
cd
createuser -s odoo
createuser -s ubuntu_user_name
exit



STEP 7
Create Odoo user and group
sudo adduser --system --home=/opt/odoo --group odoo
STEP 8
Install Gdata
cd /opt/odoo
sudo wget https://pypi.python.org/packages/a8/70/bd554151443fe9e89d9a934a7891aaffc63b9cb5c7d608972919a002c03c/gdata-2.0.18.tar.gz
sudo tar zxvf gdata-2.0.18.tar.gz
sudo chown -R odoo: gdata-2.0.18
sudo -s
cd gdata-2.0.18/
python setup.py install
exit
STEP 9
Odoo 11 Download from GitHub
cd /opt/odoo
sudo apt-get install git
sudo su - odoo -s /bin/bash
git clone https://www.github.com/odoo/odoo --depth 1 --branch 11.0 --single-branch
exit
STEP 10
Create Odoo Log File
sudo mkdir /var/log/odoo
sudo chown -R odoo:root /var/log/odoo
STEP 11
Edit Odoo configuration file
sudo gedit /etc/odoo.conf

#Copy this lines and change with users and password 
------------------------------------

[options]

; This is the password that allows database operations:

; admin_passwd = admin

db_host = False

db_port = False

db_user = odoo

db_password = False

logfile = /var/log/odoo/odoo-server.log

addons_path = /opt/odoo/addons,/opt/odoo/odoo/addons

---------------------------------------------------

sudo chown odoo: /etc/odoo.conf
STEP 12
sudo apt-get -f install
sudo wget https://github.com/wkhtmltopdf/wkhtmltopdf/releases/download/0.12.1/wkhtmltox-0.12.1_linux-trusty-amd64.deb
sudo dpkg -i wkhtmltox-0.12.1_linux-trusty-amd64.deb
sudo cp /usr/local/bin/wkhtmltoimage /usr/bin/wkhtmltoimage
sudo cp /usr/local/bin/wkhtmltopdf /usr/bin/wkhtmltopdf
STEP 13
Run Odoo Server
cd /opt/odoo/odoo

./odoo-bin
STEP 14
Open browser on :
http://localhost:8069

step 15 
manage users for database control

sudo su postgres
psql

ALTER USER pgadmin WITH PASSWORD '1234';
ALTER USER pgadmin WITH SUPERUSER ;
ALTER pgadmin pgadmin WITH SUPERUSER ;
ALTER odoo pgadmin WITH SUPERUSER ;

install Pgamidn3 from https://community.linuxmint.com/software/view/pgadmin3




