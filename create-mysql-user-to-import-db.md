```sh
CREATE USER 'root2'@'localhost' IDENTIFIED BY 'Api!@3456';
```
```sh
GRANT CREATE, DROP, ALTER ON *.* TO 'root2'@'localhost';
```
```sh
GRANT SELECT, INSERT, UPDATE, DELETE ON *.* TO 'root2'@'localhost';```
```
```sh
FLUSH PRIVILEGES;
```
```sh
mysql -u dbadmin -p 
CREATE DATABASE testdb;
DROP DATABASE testdb;
