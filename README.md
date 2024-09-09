# -WiFi-Network-Attack-Intrusion-Reconnaissance-Monitoring

Project Overview
In this project I will be demonstrating a Network Attack with my home wifi; the intruder will find my network, gain access, scan my local devices, and start tapping the outbound traffic of a target device through ARP Poisoning.


1. Setup
For this project I will be using Parrot OS combined with a network adapter and the tools below.

airodump-ng
aireplay-ng
hashcat
nmap
ettercap
wireshark

2. Reconnaissance
   
Set the adapter in monitor mode and use airodump-ng to monitor networks within range. Target a network and get their BSSID and operating channel.
Use airodump to associate clients with a given access point, get the client MAC address, and set a dumpfile to start collecting their network traffic/comms.

<img width="845" alt="Screenshot 2024-09-09 at 11 13 55 AM" src="https://github.com/user-attachments/assets/f09aab8e-2fde-44be-a0af-eb484158ffb1">
<img width="837" alt="Screenshot 2024-09-09 at 11 14 41 AM" src="https://github.com/user-attachments/assets/48dc0e55-ffce-458b-8511-430ca53dfd4e">

3. De-authentication Attack
use aireplay-ng to target a client, and send deauthentication packets to disassociate them with the AP, knocking them off the network.

<img width="837" alt="Screenshot 2024-09-09 at 11 16 34 AM" src="https://github.com/user-attachments/assets/620ff626-dc8b-499e-9596-74f8ac896392">



4. Capture EAPOL Handshake
As the device reconnects to their trusted network, airodump will capture the WPA handshake between the client and the AP; you can verify all parts of the EAPOL message in Wireshark.

<img width="832" alt="Screenshot 2024-09-09 at 11 17 27 AM" src="https://github.com/user-attachments/assets/0fbf095e-d6f7-473a-bdaf-d1596bf267f3">

<img width="837" alt="Screenshot 2024-09-09 at 11 17 51 AM" src="https://github.com/user-attachments/assets/24064361-596e-4cf0-a87b-c38dc032ca1c">




5. Hashcat Password Attack
Convert the file to be used with hashcat, and use a dictionary attack with a well known wordlist 'rockyou', combined with a rule list 'best64'.
Weak or previously breached passwords will be cracked, and written out with the associated hash.

<img width="837" alt="Screenshot 2024-09-09 at 11 19 30 AM" src="https://github.com/user-attachments/assets/0b2cda08-19d4-4e33-acc6-6eb149c3d235">


<img width="838" alt="Screenshot 2024-09-09 at 11 19 51 AM" src="https://github.com/user-attachments/assets/a02798f2-3435-4542-bab7-8760bd23aa5b">

6. Reconnaissance
Access the network with the cracked password, run ifconfig to get local IP, use nmap to scan the network.
nmap can be used to scan for vulnerabilities, scan hosts, and choose a weak target.


<img width="869" alt="Screenshot 2024-09-09 at 11 22 19 AM" src="https://github.com/user-attachments/assets/ba5c8ea6-11a9-44cb-926e-40497f0b9247">

7. Arp Poisoning, MiTM
Use ettercap to create a man-in-the-middle attack, I am now sitting inbetween the router and the client, secretly forwarding & capturing the traffic.

<img width="844" alt="Screenshot 2024-09-09 at 11 24 16 AM" src="https://github.com/user-attachments/assets/f3f87038-f9de-4418-8e69-0c8753da5e33">

8. Packet Analysis
Wireshark can be used for detailed packet capture and packet analysis.
online tools can be used to analyze .pcap for ease of use.


<img width="840" alt="Screenshot 2024-09-09 at 11 25 43 AM" src="https://github.com/user-attachments/assets/b99c2c7e-1249-4f73-a569-67828d2622a1">





<img width="829" alt="Screenshot 2024-09-09 at 11 26 28 AM" src="https://github.com/user-attachments/assets/676ae258-4410-4126-9fe3-80693cbdfb9b">



<img width="833" alt="Screenshot 2024-09-09 at 11 26 46 AM" src="https://github.com/user-attachments/assets/382c01d3-78dd-428a-9d40-e302b99e8617">












