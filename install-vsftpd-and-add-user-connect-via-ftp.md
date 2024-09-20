### INSTALL FTP ON UBUNTU VPS

```sh
apt update
apt upgrade
```
- Install VSFTPD
```sh
apt install vsftpd
```
#### Now need to edit configration file

```sh
nano /etc/vsftpd.conf
```
#### Uncomment or write below lines inside vsftpd.conf
```sh
local_umask=022
local_enable=YES
write_enable=YES
chroot_local_user=YES
user_sub_token=$USER
pasv_min_port=10000
pasv_max_port=10100
user_sub_token=$USER
user_config_dir=/etc/vsftpd_user_conf
allow_writeable_chroot=YES
pasv_address=YOUR_SERVER_IP
```
```sh
#### Restart VSFTPD
service vsftpd restart
```
NOW CREATE ROOT USER THAT POINTS TO DIRECTORY /var/www/home PATH (You may specify your own path) /////////////
```sh
sudo useradd -d /var/www/home(specify your own directory path)  -s /bin/bash newuser
echo 'newuser:YourPassword' | sudo chpasswd 
sudo chown -R newuser:newuser /var/www/home
sudo chmod -R 755 /var/www/home
```
#### Edit passwd file and verify user entry at the end (Optional)
```sh
sudo nano /etc/passwd
```
#### Create user specific file to specify directory path where user will point

```sh
sudo nano /etc/vsftpd_user_conf/newuser
```
##### Paste below line inside the file and save the file
```sh
local_root=/var/www/home
```
