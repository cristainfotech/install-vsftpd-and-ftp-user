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


```ssh-keygen -t rsa -b 4096 -C "your_email@example.com"```

```$private_key_path = '/var/www/.ssh/id_rsa';
$public_key_path = '/var/www/.ssh/id_rsa.pub';```

`$remote_server_ip = '103.76.122.71';`
`$remote_username = 'root';`
`$server_port = '22';`

// Establish SSH connection using the private key
`$connection = ssh2_connect($remote_server_ip, $server_port);`
`if (!$connection) {
    die('SSH connection failed.');
}`

`if (!ssh2_auth_pubkey_file(
    $connection,
    $remote_username,
    $public_key_path,
    $private_key_path
)) {
    die('SSH authentication failed.');
}`

