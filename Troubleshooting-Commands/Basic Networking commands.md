# Basic Networking Commands

Networking basics start with knowing a few simple commands. These help check your connection, IP details, and troubleshoot issues.

**1. Check your IP address and network configuration**
```
# Windows
ipconfig /all

# Linux/macOS
ifconfig
# or
ip addr show
```

This shows your IP address, subnet mask, gateway, and DNS servers. Make sure your IP is valid for your network.

----------------------------------------------------------

**2. Test network connectivity**

Ping is the easiest way to see if your computer can reach another device or website.
```
# Ping a website
ping google.com

# Ping an IP address directly
ping 8.8.8.8

# Limit the number of pings (Linux/macOS)
ping -c 4 google.com
```

A successful ping means the network is working. Failed pings indicate a connection problem.

---------------------------------------------------

**3. Trace the route to a host**

If ping works but websites are slow, tracert or traceroute helps see the path packets take and identify where delays occur.
```
# Windows
tracert google.com

# Linux/macOS
traceroute google.com
```

-----------------------------------------

**4. Check active connections**

You can see which connections are currently open or listening on your device.
```
# Windows
netstat -an

# Linux/macOS
netstat -tulnp
```

This is useful to check if applications are using the network or to troubleshoot port issues.

--------------------------------

**5. Verify DNS resolution**

If websites don’t open by name but work by IP, the DNS might be the problem.
```
# Windows
nslookup google.com

# Linux/macOS
dig google.com
```
This shows if your device can translate domain names into IP addresses.

-------------------------------

**6. Check your default gateway**

The default gateway is usually your router. If the internet isn’t working, make sure it’s correct.
```
# Windows
ipconfig | findstr /i "Gateway"

# Linux/macOS
route -n
```
-------------------------------------------------

**7. Release and renew IP (for DHCP networks)**

If you suspect an IP conflict or lost connection, renewing your IP can fix it.
```
# Windows
ipconfig /release
ipconfig /renew

# Linux
sudo dhclient -r
sudo dhclient
```
--------------------------------------------
These are the most basic networking commands that everyone should know. They help you quickly identify and solve common network issues.
