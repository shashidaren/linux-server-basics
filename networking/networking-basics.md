# Linux Networking Basics

Networking tools help administrators diagnose connectivity issues and manage network interfaces.

---

## View Network Interfaces

Show network interfaces:

ip a

Example output shows:

- interface name
- IP address
- MAC address
- interface status

---

## Show Routing Table

ip route

Displays the system's routing table and default gateway.

---

## Check IP Address

ip addr show

or

hostname -I

---

## Test Network Connectivity

Ping a host:

ping google.com

Ping a specific IP:

ping 8.8.8.8

---

## Check Open Ports

Use ss command:

ss -tuln

Options:

t → TCP  
u → UDP  
l → listening  
n → numeric output  

---

## Check Listening Services

ss -tulpn

Shows which services are listening on ports.

---

## DNS Lookup

Use dig:

dig google.com

Use nslookup:

nslookup google.com

---

## Test HTTP Connectivity

Use curl:

curl google.com

Check HTTP headers:

curl -I google.com

---

## Trace Network Route

Use traceroute:

traceroute google.com

Shows network path to destination.

---

## Check Network Interfaces Statistics

ip -s link

Shows packet statistics.

---

## Restart Network Service

RHEL-based systems:

sudo systemctl restart NetworkManager

---

## View Active Connections

ss -tunap

Displays active network connections.

---

## Troubleshooting Example

If server cannot reach internet:

1. Check IP address

ip a

2. Check routing table

ip route

3. Test connectivity

ping 8.8.8.8

4. Test DNS

dig google.com

