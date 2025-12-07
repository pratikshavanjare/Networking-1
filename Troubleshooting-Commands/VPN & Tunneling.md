# VPN & Tunneling

## 1. VPN

A VPN creates a secure and private connection over the internet.
Think of it as a private highway inside the public internet where your data travels safely.
It hides your IP, encrypts your data, and allows remote users to connect to an office network securely.

### Common VPN Types

- **Site-to-Site VPN** → Connects two office networks.
- **Remote Access VPN** → User connects from home/laptop to company network.
- **SSL VPN** → Uses HTTPS.
- **IPsec VPN** → Uses encryption & authentication.

### Important VPN Commands

**1. Create ISAKMP Policy**
```
crypto isakmp policy 10
 encryption aes 256
 hash sha256
 authentication pre-share
 group 14
```

**2. Set Pre-Shared Key**
```
crypto isakmp key mykey123 address 10.10.10.1
```

**3. IPsec Transform-Set**
```
crypto ipsec transform-set MYSET esp-aes esp-sha-hmac
```

**4. Create Crypto Map**
```
crypto map MYMAP 10 ipsec-isakmp
 set peer 10.10.10.1
 set transform-set MYSET
 match address VPN-TRAFFIC
```

**5. Apply to Interface**
```
interface g0/0
 crypto map MYMAP
```

**6. Verify**
```
show crypto isakmp sa
show crypto ipsec sa
```

----------------------------

## 2. Tunneling

Tunneling is the process of wrapping one packet inside another to send it safely across a network.
It doesn’t always encrypt — it mainly encapsulates data so it can travel through different network types.
It’s like putting a letter inside another envelope so it can pass through routes that normally don’t allow it.

- VPN uses tunneling
- Tunneling alone is not always secure

### Tunneling Commands

**1. Create Tunnel Interface**
```
interface tunnel 0
 ip address 10.1.1.1 255.255.255.252
 tunnel source 192.168.1.2
 tunnel destination 192.168.2.2
```

**2. Add static route**
```
ip route 10.2.0.0 255.255.255.0 10.1.1.2
```

**3. Verify**
```
show interface tunnel 0
show ip route
```
