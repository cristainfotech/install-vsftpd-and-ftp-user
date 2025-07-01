```sh
CREATE USER 'db-server1-usa'@'localhost' IDENTIFIED BY 'India!@3456';
```
```sh
GRANT ALL PRIVILEGES ON *.* TO 'db-server1-usa'@'localhost' WITH GRANT OPTION;
```
```sh
FLUSH PRIVILEGES;
