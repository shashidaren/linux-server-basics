# Linux Package Management

Package management allows administrators to install, update, remove, and manage software on Linux systems.

Different Linux distributions use different package managers.

RHEL / Rocky / Alma → dnf / yum  
Ubuntu / Debian → apt  

---

## Check Installed Packages

List installed packages (RHEL-based):

dnf list installed

List installed packages (Debian-based):

apt list --installed

---

## Install a Package

RHEL / Rocky / Alma:

sudo dnf install package_name

Example:

sudo dnf install nginx

Debian / Ubuntu:

sudo apt install nginx

---

## Remove a Package

RHEL-based:

sudo dnf remove package_name

Debian-based:

sudo apt remove package_name

---

## Update All Packages

RHEL-based:

sudo dnf update

Debian-based:

sudo apt update
sudo apt upgrade

---

## Search for Packages

RHEL-based:

dnf search package_name

Example:

dnf search nginx

Debian-based:

apt search nginx

---

## Show Package Information

RHEL-based:

dnf info package_name

Example:

dnf info nginx

Debian-based:

apt show nginx

---

## Check Package Dependencies

RHEL-based:

dnf deplist package_name

Example:

dnf deplist nginx

---

## Install Package from Local RPM

sudo rpm -ivh package.rpm

Upgrade package:

sudo rpm -Uvh package.rpm

Remove package:

sudo rpm -e package_name

---

## Verify Installed Package

rpm -qa | grep package_name

Example:

rpm -qa | grep nginx

---

## Clean Package Cache

RHEL-based:

sudo dnf clean all

Debian-based:

sudo apt clean

---

## Check Enabled Repositories

RHEL-based:

dnf repolist

Debian-based:

ls /etc/apt/sources.list.d/

---

## Troubleshooting Package Issues

Check repositories:

dnf repolist

Clean metadata cache:

sudo dnf clean all

Rebuild cache:

sudo dnf makecache

Check package version:

rpm -qi package_name

