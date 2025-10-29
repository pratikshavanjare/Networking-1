## Ping Frame Analysis

### Tasks: 

<img width="1747" height="222" alt="image" src="https://github.com/user-attachments/assets/93137423-e409-485e-a509-466713310b5d" />

Scenario:

PC1 pings PC2. Answer the following questions based on the echo request message sent from PC1 to PC2.


1) What is the destination MAC address in the frame at A in the network?
   
   a) PC1's MAC address

   b) PC2's MAC address

   c) Switch1's G1/0/1 MAC address

   d) Switch2's G1/0/2 MAC address

   e) Router1's G0/0/0 MAC address

   f) Router1's Se0/1/0 MAC address

   g) Router2's G0/0/0 MAC address

   h) Router2's Se0/1/0 MAC address

   i) Switch2's G1/0/1 MAC address

   j) Switch2's G0/0/0 MAC address

   k) There is no MAC address

   **Your Answer**: The answer is "e" because when PC1 sends data to another network, so it first sends it to its router. That’s why the destination MAC is the  router’s interface (G0/0/0) connected to PC1.
   ```
   R1> en
   R1# sh run
   !
   !
   !
   interface GigabitEthernet0/0/0
   mac-address 0010.aaaa.aaaa
   ip address 10.1.1.254 255.255.255.0
    ```

---

2) What is the destination MAC address at A in the network?
   
   **Your Answer**: mac-address 0010.aaaa.aaaa

---

3) What encapsulation is used at A in the network?

   **Your Answer**: Ethernet II (PC1 and Router1 are connected in a **LAN**, so they use **Ethernet** to send data)


--------------
4) What is the destination MAC address in the frame at C in the network?
   
   a) PC1's MAC address

   b) PC2's MAC address

   c) Switch1's G1/0/1 MAC address

   d) Switch2's G1/0/2 MAC address

   e) Router1's G0/0/0 MAC address

   f) Router1's Se0/1/0 MAC address

   g) Router2's G0/0/0 MAC address

   h) Router2's Se0/1/0 MAC address

   i) Switch2's G1/0/1 MAC address

   j) Switch 2's G0/0/0 MAC address

   k) There is no MAC address

   **Your Answer**: The answer is "k-There is no MAC address" 

------------

5) What encapsulation is used at C in the network?

   **Your Answer**: HDLC because At point C, the connection is between Router1 and Router2 over a serial link,
and serial links use HDLC encapsulation to send data.

------------

6) What is the destination MAC address in the frame at D in the network?
   
   a) PC1's MAC address

   b) PC2's MAC address

   c) Switch1's G1/0/1 MAC address

   d) Switch2's G1/0/2 MAC address

   e) Router1's G0/0/0 MAC address

   f) Router1's Se0/1/0 MAC address

   g) Router2's G0/0/0 MAC address

   h) Router2's Se0/1/0 MAC address

   i) Switch2's G1/0/1 MAC address

   j) Switch 2's G0/0/0 MAC address

   k) There is no MAC address

   **Your Answer**: b "PC2'S MAC address

--------------

7) What is the destination MAC address at D in the network?

   **Your Answer**: 0010.2222.2222
   In the network D the destination MAC address is PC2's MAC address , So if we run a command(ipconfig/all) on PC2 it will show--


   <img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/ca6c86e4-f000-44a2-a1ef-b3510eb454e2" />


--------------
8) What encapsulation is used at D in the network?

   **Your Answer**: Ethernet II

----------------

9) What is the destination MAC address in the frame at E in the network?
    
   a) PC1's MAC address

   b) PC2's MAC address

   c) Switch1's G1/0/1 MAC address

   d) Switch2's G1/0/2 MAC address

   e) Router1's G0/0/0 MAC address

   f) Router1's Se0/1/0 MAC address

   g) Router2's G0/0/0 MAC address

   h) Router2's Se0/1/0 MAC address

   i) Switch2's G1/0/1 MAC address

   j) Switch 2's G0/0/0 MAC address

   k) There is no MAC address

   **Your Answer**: b) PC2's MAC address

----------------

10) What is the destination MAC address at E in the network?

    Your Answer: The MAC address will be PC2'S MAC address which is 0010.2222.2222

-------------------

11) What encapsulation is used at E in the network?

    **Your Answer**: Ethernet II

