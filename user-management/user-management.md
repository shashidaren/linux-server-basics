Then delete everything and paste this:

# Linux User Management

User management is a fundamental system administration task. It involves creating users, assigning permissions, managing groups, and maintaining secure access to the system.

---

## 1. Create a User

Create a new user account:

```bash
sudo useradd username

Example:

sudo useradd shashi
2. Create User with Home Directory
sudo useradd -m username

Home directory will be created in:

/home/username
3. Set User Password
sudo passwd username

Example:

sudo passwd shashi
4. Delete a User

Delete user:

sudo userdel username

Delete user and home directory:

sudo userdel -r username
5. Modify a User

Change login shell:

sudo usermod -s /bin/bash username

Change home directory:

sudo usermod -d /home/newdir username
6. User Groups

Create group:

sudo groupadd devops

Add user to group:

sudo usermod -aG devops username

Check user groups:

groups username
7. System Users vs Regular Users

Regular users:

UID usually starts from 1000+

System users:

UID usually below 1000

View users:

cat /etc/passwd
8. Important User Files

User information:

/etc/passwd

Encrypted passwords:

/etc/shadow

Group information:

/etc/group
9. Lock and Unlock Users

Lock account:

sudo usermod -L username

Unlock account:

sudo usermod -U username
10. Check Logged in Users

Show logged-in users:

who

Show detailed login activity:

w

Show login history:

last
11. Switch User (su vs sudo)

Switch to another user:

su username

Switch to root with full environment:

su -
12. Using sudo

Example:

sudo dnf update

Grant sudo privileges (RHEL-based systems):

sudo usermod -aG wheel username

Verify:

groups username
13. Edit sudoers Safely

Always use:

sudo visudo

Example entry:

shashi ALL=(ALL) ALL

Meaning:

user shashi

can run commands

as any user

on any host

14. Password Aging

Check password settings:

chage -l username

Set password expiry:

sudo chage -M 90 username

Force password change at next login:

sudo chage -d 0 username
15. Disable Login Shell

Useful for service accounts.

sudo usermod -s /sbin/nologin username

or

sudo usermod -s /bin/false username
16. Check Failed Login Attempts

RHEL / Rocky / Alma:

sudo cat /var/log/secure

Ubuntu / Debian:

sudo cat /var/log/auth.log

Search failed logins:

sudo grep "Failed password" /var/log/secure
