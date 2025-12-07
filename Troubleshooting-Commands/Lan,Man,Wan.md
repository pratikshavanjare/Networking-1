# 1. LAN (Local Area Network)

A LAN is basically a network in a small area—like your home, office, or a single building. Devices on a LAN can talk to each other easily, share files, printers, or even an internet connection.

```
# See all devices connected in your LAN (Windows)
arp -a

# Check if a device in your LAN is reachable
ping 192.168.1.10
```

Think of a LAN like all the computers and phones in your house talking to each other over Wi-Fi or cable. It’s fast because everything is nearby.

-----------------------------------------

## 2. MAN (Metropolitan Area Network)

A MAN is bigger than a LAN. It usually covers a city or a big campus. A MAN connects multiple LANs together so that they can communicate over a larger area.
```
# Check the path to another LAN in the same city
tracert 10.10.0.5  # Windows
traceroute 10.10.0.5  # Linux/macOS
```
Think of it like several office buildings in a city connected with high-speed cables or fiber. Not as small as a LAN, but still much smaller than the internet.

-----------------------------------

## 3. WAN (Wide Area Network)

A WAN is the largest kind of network. It can cover countries or even the whole world. The internet itself is the biggest example of a WAN.
```
# Check if you can reach a website on the internet
ping google.com

# See the path your data takes to reach a server far away
tracert google.com  # Windows
traceroute google.com  # Linux/macOS
```

WANs connect multiple LANs and MANs over long distances. Since it spans so far, it’s usually slower than a LAN.

----------------------------------
