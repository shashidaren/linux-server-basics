# Linux Log Management

Logs are essential for monitoring system activity and troubleshooting problems.

Most logs are stored in the directory:

/var/log/

---

## Common Log Files

System messages:

/var/log/messages

Authentication logs:

/var/log/secure

Ubuntu authentication logs:

/var/log/auth.log

Kernel logs:

/var/log/dmesg

Boot logs:

/var/log/boot.log

---

## View Log Files

Use cat:

cat /var/log/messages

Use less for easier reading:

less /var/log/messages

---

## Monitor Logs in Real Time

Use tail:

tail -f /var/log/messages

Example monitoring SSH activity:

tail -f /var/log/secure

---

## View Recent Log Entries

Show last 20 lines:

tail -20 /var/log/messages

Show last 50 lines:

tail -50 /var/log/messages

---

## Search Logs

Search logs using grep.

Example:

grep "error" /var/log/messages

Search failed SSH logins:

grep "Failed password" /var/log/secure

---

## Systemd Logs (journalctl)

Modern Linux systems use systemd journal logs.

View all logs:

journalctl

View latest logs:

journalctl -n 50

Follow logs live:

journalctl -f

---

## View Logs for a Specific Service

Example for nginx:

journalctl -u nginx

View last 50 logs:

journalctl -u nginx -n 50

Follow logs:

journalctl -u nginx -f

---

## View Logs from Current Boot

journalctl -b

---

## View Kernel Logs

Use dmesg:

dmesg

Useful for checking:

hardware issues  
disk errors  
driver problems  

---

## Log Rotation

Logs are rotated to prevent them from filling disk space.

Configuration file:

/etc/logrotate.conf

Example logrotate directory:

/etc/logrotate.d/

Example manual rotation:

logrotate -f /etc/logrotate.conf

---

## Troubleshooting Example

If a service fails:

1. Check service status

systemctl status service_name

2. Check service logs

journalctl -u service_name

3. Check system logs

tail -f /var/log/messages

