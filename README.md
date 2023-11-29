# library-management-system
Requirements:
  JDK 17 - https://www.eclipse.org/downloads/
  eclipse - https://www.eclipse.org/downloads/
  MySQL

# MySQL Database Setup (Linux):
sudo apt install mysql
(or: sudo apt install mariadb)

sudo systemctl start mysql
(start the database service)

sudo mysql_secure_installation
(run installation script and set root user password)

// navigate to the directory containing the sql files (3 tables)

mysql -u root -p
(connect to the database)

Create database test;
(create the database in mysql)

use test;

source librarian.sql;
source books.sql;
source issuedbooks.sql;
(create the tables by importing the files)

USER '<username>'@'localhost' IDENTIFIED BY '<password>';
(put a user that connect from localhost, if you don't want to use your root user)

GRANT ALL PRIVILEGES ON your_database.* TO '<username>'@'localhost';
(grant privileges to the user)

FLUSH PRIVILEGES;
(flush to apply changes)

# Usage:
clone this repo https://github.com/mohamad522/library-management-system/tree/master

in eclipse:
file —> import —> General —> Existing Projects into Workspace
click next
choose the directory where you downloaded the project (ex. /home/user/downloads)
Finish

now edit the connection file:
  In this file; Library/src/(default package)/DB.java:
  edit getConnection() function to connect to your mysql database via username and password:
  con=DriverManager.getConnection("jdbc:mysql://localhost:3306/test","<username>","<password>");

run the code in eclipse

Login as admin with:
Username: admin
Password: admin123
