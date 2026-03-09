# Linux System Monitoring

System monitoring tools help administrators observe system performance and identify resource bottlenecks.

---

## Check System Load

uptime

Example output:

load average: 0.20, 0.35, 0.40

These values represent system load over:

1 minute  
5 minutes  
15 minutes

---

## Monitor Processes in Real Time

top

Displays:

CPU usage  
memory usage  
running processes  

Press q to quit.

---

## Improved Monitoring Tool

Install htop:

sudo dnf install htop

Run:

htop

Provides interactive process management.

---

## Check Memory Usage

free -h

Displays:

total memory  
used memory  
available memory  

---

## CPU Statistics

vmstat 1

Shows:

CPU usage  
memory  
process activity  

Updated every second.

---

## Disk I/O Monitoring

iostat

Install if needed:

sudo dnf install sysstat

Run:

iostat -x 1

Shows disk read/write performance.

---

## Monitor Network Usage

ss -s

Shows network socket statistics.

---

## Check Disk Usage

df -h

Displays disk usage for mounted filesystems.

---

## Check Directory Usage

du -sh /var

Useful for identifying large directories.

---

## Identify High CPU Processes

ps -eo pid,ppid,cmd,%mem,%cpu --sort=-%cpu | head

Shows processes using the most CPU.

---

## Identify High Memory Processes

ps -eo pid,ppid,cmd,%mem,%cpu --sort=-%mem | head

Shows processes using the most memory.

---

## Monitor System Activity

sar

Example:

sar -u 1 5

Shows CPU usage every second for 5 seconds.

---

## Troubleshooting Example

If a system becomes slow:

1. Check system load

uptime

2. Identify heavy processes

top

3. Check memory usage

free -h

4. Check disk I/O

iostat

