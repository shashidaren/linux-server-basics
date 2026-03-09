# Linux Firewall Management (firewalld)

Firewalld is the default firewall management tool in many modern Linux distributions such as RHEL, Rocky Linux, AlmaLinux, and CentOS.

It controls incoming and outgoing network traffic using zones and rules.

---

## Check Firewall Status

Check if firewalld is running:

sudo systemctl status firewalld

---

## Start Firewall

sudo systemctl start firewalld

Enable firewall at boot:

sudo systemctl enable firewalld

---

## Stop Firewall

sudo systemctl stop firewalld

---

## Check Firewall State

firewall-cmd --state

Expected output:

running

---

## List Active Zones

firewall-cmd --get-active-zones

---

## List Firewall Rules

firewall-cmd --list-all

---

## Allow a Service

Allow HTTP:

sudo firewall-cmd --add-service=http

Allow HTTPS:

sudo firewall-cmd --add-service=https

---

## Make Rule Permanent

sudo firewall-cmd --add-service=http --permanent

Reload firewall:

sudo firewall-cmd --reload

---

## Allow Specific Port

Example: allow port 8080

sudo firewall-cmd --add-port=8080/tcp

Permanent rule:

sudo firewall-cmd --add-port=8080/tcp --permanent

Reload firewall:

sudo firewall-cmd --reload

---

## Remove Service

sudo firewall-cmd --remove-service=http

Permanent removal:

sudo firewall-cmd --remove-service=http --permanent

---

## Remove Port

sudo firewall-cmd --remove-port=8080/tcp

---

## List Allowed Services

firewall-cmd --list-services

---

## List Open Ports

firewall-cmd --list-ports

---

## Reload Firewall Rules

sudo firewall-cmd --reload

---

## Check Default Zone

firewall-cmd --get-default-zone

---

## Change Default Zone

sudo firewall-cmd --set-default-zone=public

---

## Troubleshooting Firewall

Check firewall status:

systemctl status firewalld

Check open ports:

ss -tuln

Verify firewall rules:

firewall-cmd --list-all

