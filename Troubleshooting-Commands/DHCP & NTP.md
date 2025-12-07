# DHCP & NTP

## 1. DHCP (Dynamic Host Configuration Protocol)

DHCP is the service that automatically gives IP addresses to devices.
Instead of manually setting IP, subnet, gateway, DNS on every device, DHCP does it for you.

How it helps:

- Saves time
- Avoids IP conflicts
- Makes networks easier to manage

**Simple Cisco Commands (DHCP Server):**
```
  ip dhcp pool OFFICE
 network 192.168.1.0 255.255.255.0
 default-router 192.168.1.1
 dns-server 8.8.8.8
```

**Check DHCP bindings:**
```
show ip dhcp binding
```

--------------------------------------------------------

## 2. NTP (Network Time Protocol)

NTP keeps all devices on the network time-synchronized.
Routers, switches, servers, logs—everything stays in perfect time so troubleshooting and security logs match correctly.

**Why NTP is important:**

- Accurate logs
- Secure communication
- Scheduling tasks
- Avoids time mismatches in networks

**Simple Cisco Commands (Set NTP Server):**
```
ntp server 192.168.1.100
```

**Check NTP status:**
```
show ntp status
```
