# sampleflaskapp

Install PIP on RHEL7:
wget https://files.pythonhosted.org/packages/b0/d1/8acb42f391cba52e35b131e442e80deffbb8d0676b93261d761b1f0ef8fb/setuptools-40.6.2.zip
unzip setuptools-40.6.2.zip 
cd setuptools-40.6.2
python setup.py install

wget https://bootstrap.pypa.io/get-pip.py
python get-pip.py

2. Install modules using PIP
pip install flask
pip install flask_mysqldb
pip install wtforms
pip install passlib

3. Install wsgi modules
yum install mod_wsgi

4. Install MariaDB client and server
yum install mariadb mariadb-server
mysql_secure_installation

5. MySQL
mysql -u root -pxxxxxx

Useful:
SELECT host,user,password,Grant_priv,Super_priv FROM mysql.user;
mysql -u root -pxxxxxx -D myflaskapp -e "SELECT * FROM users;"
mysql -u root -pxxxxxx -D myflaskapp -e "DELETE FROM users WHERE id=13;"

Todo:
GRANT ALL ON myflakapp.* TO root@'%' IDENTIFIED BY 'passwd';
UPDATE mysql.user SET Grant_priv='Y', Super_priv='Y' WHERE User='username';
FLUSH PRIVILEGES;


mysql -u root -pxxxxxx
SHOW DATABASES;
CREATE DATABASE myflaskapp;
USE myflaskapp;
CREATE TABLE users(id INT(11) AUTO_INCREMENT PRIMARY KEY,name VARCHAR(100), email VARCHAR(100), username VARCHAR(30), password VARCHAR(100), register_date TIMESTAMP DEFAULT CURRENT_TIMESTAMP);
SHOW TABLES;
DESCRIBE users;
USE myflaskapp;
SELECT * FROM users;

CREATE TABLE articles (id INT(11) AUTO INCREMENT PRIMARY KEY, title VARCHAR(255), author VARCHAR(100), body TEXT, create_date TIMESTAMP DEFAULT CURRENT_TIMESTAMP);

systemctl restart mariadb
