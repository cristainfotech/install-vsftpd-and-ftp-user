### INSTALL FTP ON UBUNTU VPS


apt update
apt upgrade
////INSTALL VSFTPD ///

apt install vsftpd
nano /etc/vsftpd.conf
// write below inside vsftpd.conf
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

service vsftpd restart

//////////


//////// CREATE ROOT USER /////////////
sudo useradd -d /var/www/home -s /bin/bash rootuser
echo 'rootuser:India12!@' | sudo chpasswd 
sudo chown -R rootuser:rootuser /var/www/home
sudo chmod -R 755 /var/www/home
sudo nano /etc/passwd
sudo nano /etc/vsftpd_user_conf/rootuser
local_root=/var/www/home
