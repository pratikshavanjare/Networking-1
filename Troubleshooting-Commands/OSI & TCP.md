# OSI Model & TCP/IP Model

## 1. OSI Model (7 Layers)

The OSI model explains network communication step by step, from user apps to physical wires.

**Layer 1 – Physical Layer**

It deals with cables, signals, connectors, Wi-Fi signals, etc.
If this layer is broken, nothing will work.
```
# Check if network cable/Wi-Fi is detected (Windows)
ipconfig

# Check interface status (Linux)
ip link show
```

**Layer 2 – Data Link Layer**

Handles MAC addresses and device-to-device communication inside a LAN.
```
# View MAC addresses around you
arp -a

# Check your device MAC
ipconfig /all   # Windows
ifconfig        # Linux/macOS
```

**Layer 3 – Network Layer**

Responsible for IP addresses and routing data between networks.
```
# Check your IP
ipconfig       # Windows
ip addr show   # Linux

# Check route
route print    # Windows
route -n       # Linux
```

**Layer 4 – Transport Layer**

Controls data delivery, using TCP and UDP ports.
```
# Check open ports and connections
netstat -an

# Test port connectivity
telnet <IP> <port>
```

**Layer 5 – Session Layer**

Creates and manages communication sessions.
```
ssh user@IP
telnet IP port
```

**Layer 6 – Presentation Layer**

Handles data formatting, encryption, compression.

**Examples:**

HTTPS

SSL/TLS certificates

(No direct commands, but SSL check tools exist.)

**Layer 7 – Application Layer**

This is where users interact (browsers, apps).
```
# Check website response
ping google.com

# Get webpage headers
curl -I https://google.com
```
------------------------------

## 2. TCP/IP Model (4 Layers)

The TCP/IP model is a simplified version used in real networks today.

**Layer 1 – Network Access (Link Layer)**

Handles MAC, Wi-Fi, LAN communication.
```
arp -a
ifconfig
```

**Layer 2 – Internet Layer**

It handles IP addresses, routing, packet movement.
```
ipconfig / ifconfig      # Check IP
ping 8.8.8.8             # Test internet
tracert google.com       # Windows
traceroute google.com    # Linux/macOS
```

**Layer 3 – Transport Layer**

Handles TCP & UDP communication, ports, reliability.
```
netstat -an
telnet IP port
```

**Layer 4 – Application Layer**

User-level applications—browsers, email, FTP.
```
curl google.com
ping google.com
```

