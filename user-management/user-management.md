# Linux User Management

User management is a fundamental system administration task. It involves creating users, assigning permissions, managing groups, and maintaining secure access to the system.

---

## Create a User

sudo useradd username

Example:

sudo useradd shashi

---

## Create User with Home Directory

sudo useradd -m username

Home directory will be created in:

/home/username

---

## Set User Password

sudo passwd username

Example:

sudo passwd shashi

---

## Delete a User

Delete user:

sudo userdel username

Delete user and home directory:

sudo userdel -r username

---

## Modify a User

Change login shell:

sudo usermod -s /bin/bash username

Change home directory:

sudo usermod -d /home/newdir username

---

## User Groups

Create group:

sudo groupadd devops

Add user to group:

sudo usermod -aG devops username

Check user groups:

groups username

---

## System Users vs Regular Users

Regular users usually have UID starting from 1000.

System users usually have UID below 1000.

View users:

cat /etc/passwd

---

## Important User Files

User information:

/etc/passwd

Encrypted passwords:

/etc/shadow

Group information:

/etc/group

---

## Lock and Unlock Users

Lock account:

sudo usermod -L username

Unlock account:

sudo usermod -U username

---

## Check Logged in Users

who

w

last

---

## Switch User

su username

Switch to root:

su -

---

## Using sudo

Example:

sudo dnf update

Grant sudo privileges:

sudo usermod -aG wheel username

Verify groups:

groups username

---

## Edit sudoers Safely

sudo visudo

Example entry:

shashi ALL=(ALL) ALL

---

## Password Aging

Check password policy:

chage -l username

Set password expiry:

sudo chage -M 90 username

Force password change:

sudo chage -d 0 username

---

## Disable Login Shell

sudo usermod -s /sbin/nologin username

or

sudo usermod -s /bin/false username

---

## Check Failed Login Attempts

RHEL based systems:

sudo cat /var/log/secure

Ubuntu / Debian:

sudo cat /var/log/auth.log

Search failed logins:

sudo grep "Failed password" /var/log/secure
