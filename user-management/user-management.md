# Linux User Management

User management is a fundamental system administration task. It involves creating users, assigning permissions, managing groups, and maintaining secure access to the system.

---

# 1. Create a User

Create a new user account:

sudo useradd username

Example:

sudo useradd shashi

---

# 2. Create User with Home Directory

Some systems require explicitly creating the home directory.

sudo useradd -m username

Home directory will be created in:

/home/username

---

# 3. Set User Password

Set or change password:

sudo passwd username

Example:

sudo passwd shashi

---

# 4. Delete a User

Remove a user:

sudo userdel username

Remove user and home directory:

sudo userdel -r username

---

# 5. Modify a User

Change user properties.

Example: change login shell

sudo usermod -s /bin/bash username

Example: change home directory

sudo usermod -d /home/newdir username

---

# 6. User Groups

Groups allow multiple users to share permissions.

Create group:

sudo groupadd devops

Add user to group:

sudo usermod -aG devops username

Check user groups:

groups username

---

# 7. System Users vs Regular Users

Regular users

UID usually starts from:

1000+

System users

Used for services like nginx, mysql.

UID usually below:

1000

View users:

cat /etc/passwd

---

# 8. Important User Files

User information:

/etc/passwd

Encrypted passwords:

/etc/shadow

Group information:

/etc/group

---

# 9. Lock and Unlock Users

Lock account:

sudo usermod -L username

Unlock account:

sudo usermod -U username

---

# 10. Check Logged in Users

Show logged in users:

who

Show detailed login activity:

w

Show login history:

last

11. Switch User (su vs sudo)
Switch to another user
su username

Example:

su shashi

Switch to root:

su -

The - loads the user's full login environment.

Using sudo

sudo allows a permitted user to execute commands as another user (usually root).

Example:

sudo dnf update

This is safer than logging in as root.

12. Configure sudo Access

To grant sudo privileges, add the user to the wheel group (RHEL-based systems).

sudo usermod -aG wheel username

Example:

sudo usermod -aG wheel shashi

Verify:

groups shashi
Editing sudoers File

Use visudo to safely edit sudo permissions.

sudo visudo

Example entry:

shashi ALL=(ALL) ALL

Meaning:

user shashi

can run commands

as any user

on any host

13. Password Aging

Password policies can enforce password changes.

View password settings:

chage -l username

Example:

chage -l shashi

Set password expiry:

sudo chage -M 90 username

Meaning password expires in 90 days.

14. Force Password Change

Force user to change password at next login:

sudo chage -d 0 username

Example:

sudo chage -d 0 shashi

15. Disable User Login Shell

Sometimes service accounts should not allow login.

Example:

sudo usermod -s /sbin/nologin username

or

sudo usermod -s /bin/false username

16. Check Failed Login Attempts

Check authentication logs.

RHEL / Rocky / Alma:

sudo cat /var/log/secure

Ubuntu / Debian:

sudo cat /var/log/auth.log

Example search:

sudo grep "Failed password" /var/log/secure
