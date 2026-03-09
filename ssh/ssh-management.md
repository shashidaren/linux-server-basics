# Linux SSH Server Management

SSH (Secure Shell) is used to securely access remote Linux systems.

Default SSH port: 22

---

## Connect to Remote Server

Basic connection:

ssh username@server_ip

Example:

ssh shashi@192.168.1.10

---

## Connect Using Specific Port

ssh -p 2222 username@server_ip

---

## Generate SSH Key Pair

Generate key:

ssh-keygen

Default key location:

~/.ssh/id_rsa
~/.ssh/id_rsa.pub

---

## Copy SSH Key to Server

Use ssh-copy-id:

ssh-copy-id username@server_ip

This enables passwordless login.

---

## Manual Key Setup

Copy public key:

cat ~/.ssh/id_rsa.pub

Add it to remote server:

~/.ssh/authorized_keys

---

## SSH Configuration File

Main configuration file:

/etc/ssh/sshd_config

---

## Restart SSH Service

sudo systemctl restart sshd

Check status:

systemctl status sshd

---

## Disable Root Login

Edit configuration:

sudo nano /etc/ssh/sshd_config

Set:

PermitRootLogin no

Restart SSH:

sudo systemctl restart sshd

---

## Change SSH Port

Edit ssh configuration:

/etc/ssh/sshd_config

Change:

Port 22

Example:

Port 2222

Restart SSH service.

---

## Allow Specific Users

Edit sshd_config:

AllowUsers shashi admin

---

## Disable Password Authentication

Use key authentication only.

Edit:

PasswordAuthentication no

Restart SSH.

---

## Check SSH Logs

RHEL based systems:

/var/log/secure

Ubuntu / Debian:

/var/log/auth.log

Example search:

grep ssh /var/log/secure

---

## Troubleshooting SSH

Check service:

systemctl status sshd

Check port:

ss -tulpn | grep ssh

Check firewall rules.

