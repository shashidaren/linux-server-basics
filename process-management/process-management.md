# Linux Process Management

Processes are running programs in Linux. Managing processes is a key task for system administrators when monitoring system performance and troubleshooting issues.

---

## View Running Processes

Show running processes:

ps

Show detailed process list:

ps aux

Example:

ps aux | less

---

## Process Tree

Display processes in tree format:

pstree

---

## Real-Time Process Monitoring

Use top to view system activity:

top

Shows:

CPU usage  
memory usage  
running processes  

---

## Improved Process Viewer

Install htop:

sudo dnf install htop

Run:

htop

Provides interactive process monitoring.

---

## Find a Specific Process

Use grep with ps:

ps aux | grep nginx

Example:

ps aux | grep ssh

---

## Kill a Process

Kill process using PID.

Example:

kill 1234

---

## Force Kill a Process

Use SIGKILL:

kill -9 1234

---

## Kill Process by Name

pkill nginx

Kill all processes by name:

killall nginx

---

## Process Priority

Processes have priority levels that affect CPU scheduling.

Check priority:

top

Look for the NI (nice value).

---

## Start Process with Priority

nice -n 10 command

Example:

nice -n 10 tar -czf backup.tar.gz /data

Higher nice value = lower priority.

---

## Change Process Priority

Use renice:

renice 10 -p 1234

---

## Check System Load

Use uptime:

uptime

Example output:

load average: 0.20, 0.35, 0.40

Represents system load over:

1 minute  
5 minutes  
15 minutes

---

## Check Memory Usage

free -h

---

## Identify High CPU Processes

top

or

ps -eo pid,ppid,cmd,%mem,%cpu --sort=-%cpu | head

---

## Identify High Memory Processes

ps -eo pid,ppid,cmd,%mem,%cpu --sort=-%mem | head

---

## Troubleshooting Example

If a system is slow:

1. Check system load

uptime

2. Identify heavy processes

top

3. Kill runaway process if needed

kill -9 PID

