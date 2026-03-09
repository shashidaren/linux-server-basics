# Linux Service Management with systemd

Systemd is the init system used by most modern Linux distributions. It manages system services and system startup.

---

## Check Service Status

View status of a service:

systemctl status service_name

Example:

systemctl status sshd

---

## Start a Service

Start a service:

sudo systemctl start service_name

Example:

sudo systemctl start nginx

---

## Stop a Service

sudo systemctl stop service_name

Example:

sudo systemctl stop nginx

---

## Restart a Service

sudo systemctl restart service_name

---

## Reload a Service

Reload configuration without full restart:

sudo systemctl reload service_name

Example:

sudo systemctl reload nginx

---

## Enable Service at Boot

Enable service to start automatically when system boots:

sudo systemctl enable service_name

Example:

sudo systemctl enable nginx

---

## Disable Service at Boot

sudo systemctl disable service_name

---

## Check if Service is Enabled

systemctl is-enabled service_name

---

## List All Services

systemctl list-units --type=service

---

## List Failed Services

systemctl --failed

---

## View Service Logs

Use journalctl to view logs.

Example:

journalctl -u nginx

View latest logs:

journalctl -u nginx -n 50

Follow logs in real time:

journalctl -u nginx -f

---

## Reload systemd Configuration

If a service file changes:

sudo systemctl daemon-reload

---

## Service Unit Files

Service files are located in:

/usr/lib/systemd/system/

/etc/systemd/system/

Example:

nginx.service

---

## Example Custom Service

Example systemd service file:

[Unit]
Description=My Application

[Service]
ExecStart=/usr/bin/python3 /opt/app/app.py
Restart=always

[Install]
WantedBy=multi-user.target

---

## Troubleshooting Services

Check service status:

systemctl status service_name

Check logs:

journalctl -u service_name

Check failed services:

systemctl --failed

