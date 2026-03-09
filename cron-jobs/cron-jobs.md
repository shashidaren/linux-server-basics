# Linux Cron Jobs (Task Scheduling)

Cron is used to schedule automated tasks in Linux. It allows administrators to run commands or scripts at specific times.

---

## Edit Cron Jobs

Edit the current user's crontab:

crontab -e

---

## View Cron Jobs

List scheduled cron jobs:

crontab -l

---

## Remove Cron Jobs

Delete all cron jobs:

crontab -r

---

## Cron Job Format

Cron jobs use the following format:

* * * * * command

Fields represent:

minute hour day-of-month month day-of-week command

Example:

0 2 * * * /home/user/backup.sh

Meaning:

Run backup.sh every day at 2:00 AM.

---

## Common Cron Examples

Run every minute:

* * * * * command

Run every hour:

0 * * * * command

Run every day at midnight:

0 0 * * * command

Run every Sunday at 3 AM:

0 3 * * 0 command

Run every Monday at 8 AM:

0 8 * * 1 command

---

## Run Script with Cron

Example script:

/home/shashi/scripts/backup.sh

Cron entry:

0 1 * * * /home/shashi/scripts/backup.sh

This runs every day at 1 AM.

---

## Log Cron Output

Redirect output to log file:

0 1 * * * /home/shashi/scripts/backup.sh >> /var/log/backup.log 2>&1

---

## System Wide Cron Jobs

System cron configuration:

/etc/crontab

Cron directories:

/etc/cron.hourly/
/etc/cron.daily/
/etc/cron.weekly/
/etc/cron.monthly/

Example script placed in:

/etc/cron.daily/

Will run once per day.

---

## Check Cron Service

Check status:

systemctl status crond

Start service:

sudo systemctl start crond

Enable at boot:

sudo systemctl enable crond

---

## Troubleshooting Cron Jobs

Check cron logs:

grep CRON /var/log/messages

Verify cron service:

systemctl status crond

Ensure script is executable:

chmod +x script.sh

