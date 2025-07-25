# Linux Network Services

## Overview

Managing network services in Linux is essential for administration, penetration testing, and secure communication. Key services include SSH, NFS, web servers (Apache & Python), and VPNs. This guide covers installation, usage, and configuration of these services.

---

## 1. SSH (Secure Shell)

### SSH Description

SSH is used for secure remote login and command execution.

### Install OpenSSH Server

```bash
sudo apt install openssh-server -y
```

### Check SSH Server Status

```bash
systemctl status ssh
```

### Connect via SSH

```bash
ssh username@<IP_address>
```

### SSH Configuration File

`/etc/ssh/sshd_config` – used to modify authentication, login, and access settings.

---

## 2. NFS (Network File System)

### NFS Description

NFS allows file sharing across networks as if local.

### Install NFS Server

```bash
sudo apt install nfs-kernel-server -y
```

### Check NFS Server Status

```bash
systemctl status nfs-kernel-server
```

### NFS Configuration File

`/etc/exports` – define shared directories and permissions.

#### Example Entry

```bash
/home/user/nfs_sharing hostname(rw,sync,no_root_squash)
```

### Mount NFS Share

```bash
mkdir ~/target_nfs
mount <IP>:/path/to/share ~/target_nfs
```

#### Example File Tree after Mount

```bash
target_nfs/
├── css.css
├── html.html
├── javascript.js
├── php.php
└── xml.xml
```

---

## 3. Web Servers

### Apache Web Server

#### Install Apache

```bash
sudo apt install apache2 -y
```

#### Apache2 Configuration File

`/etc/apache2/apache2.conf` – for global directory access settings.

#### Example Configuration Block

```apache
<Directory /var/www/html>
    Options Indexes FollowSymLinks
    AllowOverride All
    Require all granted
</Directory>
```

### Python Web Server

#### Install and Run

```bash
sudo apt install python3 -y
python3 -m http.server        # Default port 8000
python3 -m http.server 443    # Custom port
python3 -m http.server --directory /path/to/folder
```

---

## 4. VPN (OpenVPN)

### VPN Description

VPNs securely connect clients to internal networks.

### Install OpenVPN

```bash
sudo apt install openvpn -y
```

### OpenVPN Configuration File

`/etc/openvpn/server.conf` – adjust encryption, tunneling, routing, etc.

### Connect to VPN Server

```bash
sudo openvpn --config internal.ovpn
```

---

## Conclusion

Understanding and managing Linux network services such as SSH, NFS, web servers, and VPNs is vital for system administrators and penetration testers. This knowledge enhances secure communication, efficient file sharing, and safe remote access.
