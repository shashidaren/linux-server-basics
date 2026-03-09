# Linux Boot Process

The Linux boot process is the sequence of steps the system follows to start the operating system after the machine is powered on.

Understanding the boot process helps administrators troubleshoot boot failures and system startup issues.

---

## Boot Process Overview

1. BIOS / UEFI
2. Bootloader (GRUB)
3. Kernel Initialization
4. init / systemd
5. System Services
6. User Login

---

## BIOS / UEFI

The system firmware initializes hardware components such as:

CPU  
memory  
disk controllers  
keyboard  

After hardware initialization, it looks for a bootable device such as:

hard disk  
SSD  
USB device  

---

## Bootloader (GRUB)

The bootloader loads the Linux kernel.

Common bootloader:

GRUB (Grand Unified Bootloader)

Configuration file:

/boot/grub2/grub.cfg

Boot menu allows:

select kernel version  
boot different operating systems  
enter recovery mode  

---

## Linux Kernel

The kernel is loaded into memory by GRUB.

Kernel responsibilities:

hardware management  
memory management  
process scheduling  
device drivers  

Kernel then mounts the root filesystem.

---

## init / systemd

Modern Linux systems use:

systemd

systemd is the first process started by the kernel.

Process ID:

PID 1

Check:

ps -p 1

---

## Systemd Targets

Systemd uses targets instead of runlevels.

Common targets:

multi-user.target → command line mode  
graphical.target → GUI mode  
rescue.target → single-user mode  

Check default target:

systemctl get-default

---

## System Services

systemd starts required services such as:

networking  
SSH  
firewalld  
cron  

List running services:

systemctl list-units --type=service

---

## User Login

Once services start successfully, the system presents a login prompt.

Users can log in through:

console login  
SSH login  
GUI login  

---

## Boot Logs

View boot logs:

journalctl -b

View previous boot logs:

journalctl -b -1

---

## Troubleshooting Boot Issues

Check boot messages:

dmesg

Check failed services:

systemctl --failed

Check logs:

journalctl -xe

---

## Boot Time Analysis

Analyze boot time:

systemd-analyze

Show slow services:

systemd-analyze blame

