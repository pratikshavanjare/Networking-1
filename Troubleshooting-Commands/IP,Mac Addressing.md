# IP Adress & MAC Address

## 1. IP Address

An IP address is like your device’s street address. It tells other devices where to send data.

**Check your IP:**
```
# Windows
ipconfig

# Linux/macOS
ifconfig
# or
ip addr show
```

**Test connectivity:**
```
# Ping another device or website
ping 192.168.1.1   # Check your router
ping google.com    # Check internet
```

--------------------------------

## 2. MAC Address

A MAC address is like the fingerprint of your network card. It never changes and identifies your device on a network.

**Check your MAC:**
```
# Windows
ipconfig /all

# Linux/macOS
ifconfig
# or
ip link show
```

**Use MAC address for troubleshooting:**

- Check if a device is allowed on a Wi-Fi network (MAC filtering)
- Identify devices in network logs

-------------------------------------------

**Simple Troubleshooting Steps** -

1. **Check your IP:** ipconfig or ifconfig

2. **Ping your router:** ping 192.168.1.1

3. **Ping internet:** ping google.com

4. **Check your MAC:** ipconfig /all or ifconfig

5. **If IP problem:** release & renew IP (ipconfig /release + ipconfig /renew)
