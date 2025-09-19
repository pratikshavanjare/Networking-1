#  OSI Model (Open Systems Interconnection)

The **OSI Model** is a conceptual framework used to understand and standardize how different networking systems communicate with each other.  
It divides the communication system into **7 layers**, where each layer performs a specific function.

---

## 📖 The 7 Layers of the OSI Model

1. **Physical Layer**  
   - Deals with hardware, cables, switches, and transmission of raw bits (0s and 1s).  
   - Example: Ethernet cables, Hubs.  

2. **Data Link Layer**  
   - Ensures error-free transfer of data frames between nodes.  
   - Provides **MAC addressing**.  
   - Example: Switch, Bridges.  

3. **Network Layer**  
   - Handles logical addressing (**IP addresses**) and routing of data packets.  
   - Example: Routers, IPv4/IPv6.  

4. **Transport Layer**  
   - Ensures reliable delivery of data using protocols like **TCP/UDP**.  
   - Manages segmentation, flow control, and error detection.  

5. **Session Layer**  
   - Establishes, maintains, and terminates sessions between applications.  
   - Example: APIs, remote procedure calls.  

6. **Presentation Layer**  
   - Translates, encrypts, and compresses data so applications can understand.  
   - Example: SSL/TLS encryption, JPEG, MP3.  

7. **Application Layer**  
   - Closest to the user. Provides services like **email, web browsing, file transfer**.  
   - Example: HTTP, FTP, SMTP, DNS.
  
   # 🌐 OSI Model in Real-Life Examples  

## 1. WhatsApp  
- **Application Layer** → WhatsApp app (chat, calls, media sharing)  
- **Presentation Layer** → End-to-end encryption (Signal Protocol)  
- **Session Layer** → Maintains connection between user and WhatsApp server  
- **Transport Layer** →  
  - TCP → Messages, media (reliable)  
  - UDP → Voice & video calls (fast)  
- **Network Layer** → IP addresses used to send data across the internet  
- **Data Link Layer** → Uses Wi-Fi or mobile network (MAC addresses)  
- **Physical Layer** → Actual signals via Wi-Fi/4G/5G/mobile towers  

---

## 2. Web Browsing (HTTP/HTTPS)  
 - **Application Layer** → Browser uses HTTP/HTTPS to access websites  
- **Presentation Layer** → Data encryption (SSL/TLS) + format (HTML, CSS, JS)  
- **Session Layer** → Maintains session (cookies, login state)  
- **Transport Layer** → TCP (port 80 = HTTP, port 443 = HTTPS)  
- **Network Layer** → IP addresses route data between client and server  
- **Data Link Layer** → Frames sent via Wi-Fi or Ethernet (MAC address)  
- **Physical Layer** → Actual signals (radio waves, cables, fiber optics) 
---
