  
CREATE DATABASE your_database_name;  
  
SHOW DATABASES;  
  

  
SELECT User, Host FROM mysql.user;  
  
  
CREATE USER 'new_username'@'localhost' IDENTIFIED BY 'new_password';  
  
GRANT ALL PRIVILEGES ON *.* TO 'new_username'@'localhost';  
  
  
  
  
FLUSH PRIVILEGES;  
  
  
  
GRANT ALL PRIVILEGES ON mydb.* TO 'jac'@'%';

## Docker

docker run --name test -p 3306:3306 -e MYSQL_ROOT_PASSWORD=test -d mysql



docker exec -it test bash

### inside container



mysql -u root -p

mysql -h 172.17.0.3 -u root -p



CREATE DATABASE AccountData;
Query OK, 1 row affected (0.04 sec)

mysql> CREATE DATABASE MovieData; 
Query OK, 1 row affected (0.06 sec)

FLUSH PRIVILEGES;  
Query OK, 0 rows affected (0.02 sec)

mysql> GRANT ALL PRIVILEGES ON AccountData.* TO 'root'@'%';
Query OK, 0 rows affected (0.03 sec)

mysql> GRANT ALL PRIVILEGES ON MovieData.* TO 'root'@'%';
Query OK, 0 rows affected (0.03 sec)

GRANT ALL PRIVILEGES ON autohire.* TO 'root'@'%';


CREATE DATABASE autohire;

