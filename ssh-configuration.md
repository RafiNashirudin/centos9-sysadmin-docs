# Konfigurasi port SSH

## SSH

Open file sshd_config:

```
sudo nano /etc/ssh/sshd_config
```

Look for the line that contains:

```
Port 22
```

change it to:

```
Port 2222
```

# Konfigurasi port SSH Firewalld

## Firewalld

allow port 2222

```
sudo firewall-cmd --permanent --add-port=2222/tcp
```

reload firewalld

```
sudo firewall-cmd --reload
```

check firewalld

```
sudo firewall-cmd --list-all
```

# Konfigurasi port SSH SELinux

## SELinux

list port SSH SELinux

```
sudo semanage port -l | grep ssh
```

Allow port 2222 SELinux:

```
sudo semanage port -a -t ssh_port_t -p tcp 2222
```

# restart SSH service and test SSH login

## SSH

restart SSH

```
sudo systemctl restart sshd
```

uji coba login SSH

```
ssh username@<IP Your SSH> -p <Port your SSH>
```
