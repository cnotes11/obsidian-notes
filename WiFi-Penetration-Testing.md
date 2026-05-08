	## WiFi Penetration Testing
  -  WiFi Penetration Testing is the process of assessing the security of wireless networks by identifying vulnerabilities, misconfigurations, and weaknesses in authentication, encryption, and network design. A
##### Objectives
  - Identify unauthorized or rogue access points
  - Detect weak or deprecated encryption protocols
  - Capture and analyze wireless traffic
  - Test authentication and access control mechanisms
  - Evaluate network resilience against wireless attacks
#### Wardriving
   Wardriving is the practice of discovering wireless networks while moving through an area using a wireless-enabled device.
##### Purpose
  - Discover hidden SSIDS
 - Identify open or insecure networks
  - Map wireless coverage and signal strength
##### Tools
  - Kismet
  - NetStumbler
  - Airodump-ng
### Types of Wireless Networks
### WPAN (Wireless Personal Area Network)
   - Range: Approximately 10-30 feet
   - Designed for personal device communication
  - Examples: Bluetooth, Zigbee
### WLAN (Wireless Local Area Network)
  - Provides network access within a limited area (home, office, campus)
  - Uses Access Points (APs) for connectivity
  -  Based on IEEE 802.11 standards
### WMAN (Wireless Metropolitan Area Network)
  - Covers large geographic areas such as cities
  - Interconnects multiple WLANS
##### Technologies
  - IEEE 802.16 (WIMAX)
  - Cellular networks (2G, 3G, 4G, 5G)
### IEEE 802.11 Standards
   Defined by the Institute of Electrical and Electronics Engineers (IEEE), the 802.11 family specifies wireless LAN communication standards.
##### Structure
  - 802 Committee: Defines networking standards
  - 802.11 Working Group: Focuses on wireless LAN technologies
##### Common Standards
| Standard          | Frequency | Maximum Data Rate                  |
| ----------------- | --------- | ---------------------------------- |
| 802.11a           | 5 GHz     | 54 Mbps                            |
| 802.11b           | 2.4 GHz   | 11 Mbps                            |
| 802.11g           | 2.4 GHz   | 54 Mbps                            |
| 802.11n           | 2.4/5 GHz | Up to 600 Mbps                     |
| 802.11ac          | 5 GHz     | >1 Gbps                            |
| 802.11ax (WiFi 6) | 2.4/5 GHz | Improved efficiency and throughput |
  - Reference: https://en.wikipedia.org/wiki/IEEE_802.11
### WiFi Terminology
#### SSID (Service Set Identifier)
  - Human-readable network name
  - Identifies a wireless network (e.g., Office_WiFi)
#### ESSID (Extended Service Set Identifier)
  - Logical network name shared across multiple access points
  - Used in extended networks
#### BSSID (Basic Service Set Identifier)
  - Unique MAC address of the access point
  - 48-bit identifier
#### Channel (CH)
- Frequency channel used for communication
  - Common range: Channels 1-11 (2.4 GHz band)
##### Best Practice
  - Use non-overlapping channels: 1, 6, or 11
  - Avoid interference with neighboring networks
#### Encryption (ENC)
  -  Defines the security mechanism used by the network:
    - WEP (deprecated and insecure)
    - WPA (legacy)
    - WPA2 (recommended minimum)
    - WPA3 (current best practice)
#### BSS (Basic Service Set)
  - A single wireless network cell
  - Consists of one AP and connected clients
#### ESS (Extended Service Set)
  - Multiple BSS networks interconnected
  - Provides seamless coverage over a larger area
#### NAV (Network Allocation Vector)
  - Virtual carrier sensing mechanism
  - Defines a time window to avoid packet collisions
#### RTS/CTS (Request to Send / Clear to Send)
  -  Control frames used to manage transmission
  - Helps reduce collisions in congested environments
### WiFi Penetration Testing Methodology
#### 1. Reconnaissance
  - Identify available networks
  - Collect SSID, BSSID, channel, and encryption details
    - cmd :-  airodump-ng wlan0mon
#### 2. Enable Monitor Mode
   - Switch the wireless interface to monitor mode for packet capture:
     -  cmd :- airmon-ng start wlan0
#### 3. Packet Capture
  - Capture authentication handshakes and traffic:
	     - cmd :- airodump-ng -c (channel)  -bssid  (BSSID) -w capture wlan0mon
#### 4. Deauthentication Attack
 - Force clients to disconnect and reconnect to capture handshake data:
    -  cmd :- aireplay-ng  --deauth 10  -a (BSSID)  wlan0mon
#### 5. Password Cracking
   - Attempt to recover the network key using a wordlist:
    - aircrack-ng -w wordlist.txt  capture.cap
### Common Wireless Attacks
#### Deauthentication Attack
   - Disrupts client connections from the access point
 - Used to trigger handshake capture
#### Evil Twin Attack
   - Creates a rogue access point mimicking a legitimate network
   - Used to capture user credentials
#### WPA/WPA2 Handshake Capture
   - Captures authentication exchange
  - Enables offline password cracking
#### WEP Cracking
   - Exploits weak initialization vectors (IVs)
  - Easily breakable with sufficient traffic
#### Rogue Access Point
  - Unauthorized access point connected to the network
  - Often used for internal attacks
##### Security Best Practices
   - Use WPA3 or at minimum WPA2 with AES encryption
   - Disable WPS (WI-FI Protected Setup)
   - Enforce strong password policies
   - Regularly monitor wireless traffic
   - Segment networks (quest vs internal)
  - Use VPNs on untrusted networks
##### Summary
   - Wireless networks introduce unique attack surfaces
   - Understanding IEEE 802.11, channels, and encryption is essential
   - Tools such as Aircrack-ng enable effective testing
  - Security depends on proper configuration, monitoring, and user awareness
### External-WiFi-Adapters-for-Penetration-Testing
   External wireless adapters are essential for WiFi penetration testing because they provide:
   - High transmit power (extended range)
  - Monitor mode support
  - Packet injection capability (e.g., deauthentication attacks)
  - Better antenna performance compared to internal cards
#### Key Advantages of External Adapters
##### Alfa Cards (Industry Preferred)
   - Up to-300 ft broadcast range (environment dependent)
   - Reliable packet injection support
   - High output power
  - Strong Linux/Kall compatibility
##### Recommended Adapters (Quick Comparison)
| #   | Adapter                     | Chipset           | Interface |
| --- | --------------------------- | ----------------- | --------- |
| 1   | TP-Link TL-WN722N (v1 only) | Atheros AR9271    | External  |
| 2   | Alfa AWUS036NHA             | Atheros AR9271    | External  |
| 3   | Alfa AWUS036NH              | Ralink RT3070     | External  |
| 4   | Alfa AWUS1900               | Realtek RTL88XX   | External  |
| 5   | Alfa AWUS036ACH             | Realtek RTL8812AU | External  |
| 6   | Panda PAU06                 | Atheros           | External  |
| 7   | Panda PAU09                 | Ralink RT5572     | External  |
| 8   | Alfa AWUS036NEH             | Ralink RT3070     | External  |
#### Driver Installation (Realtek RTL8812A Example)
######   Install Required Packages
   - cmd :- apt update
   - cmd :-  apt install dkms git build-essential libelf-dev linux-headers-$(uname -r)
###### Install Driver
   - cmd :- apt install realtek-rtl88xxau-dkms
###### Reboot System
   - cmd :- reboot
##### Alternative Driver Method (NDIS Wrapper)
  - cmd :- apt search ndis
 - cmd :- apt-get install ndisgtk
 - cmd :- ndisgtk
#### Detailed Adapter Breakdown
##### 1. Alfa AWUS036NHA
   - Standard: 802.11n
   - Chipset: Atheros AR9271
   - Frequency: 2.4 GHz
  - Features:
      - Excellent monitor mode support
     - Strong packet injection
    - Best compatibility with Kali Linux
    - High sensitivity and range
##### 2. Alfa AWUS036ACH
   - Standard: 802.11ac (Dual Band)
   - Chipset: Realtek RTL8812AU
   - Frequency: 2.4 GHz/5 GHz
   - Features:
      - Monitor mode + injection support
     - Dual-band capability
    - Suitable for modern networks
## WiFi Pineapple
   - WiFi Pineapple is a specialized wireless auditing device developed by Hak5, widely used in penetration testing and red team operations to assess WiFi security.
  - It is designed to simulate rogue access points and exploit how devices automatically connect to known or trusted networks.
#### Core Concept
   The WiFi Pineapple works by abusing a behavior in WiFi clients:
   - Devices constantly send probe requests (e.g., "Is my home WiFi here?")
   - Pineapple responds: "Yes, I am that network"
  - Device connects automatically attacker gains control point
This technique is known as:
  - Evil Twin Attack
 - Rogue Access Point Attack
#### Key Features
##### 1. Rogue Access Point (Evil Twin)
  - Mimics legitimate WiFi networks
  - Tricks devices into connecting automatically
  - Enables traffic interception
##### 2. Karma Attack (Auto-Response)
  - Responds to all probe requests
   - Captures devices searching for known SSIDS
##### 3. Packet Capture & Analysis
  - Captures network traffic
  - Supports tools like
     - tcpdump
    - Wireshark
##### 4. Deauthentication Attacks
  - Forces clients off real AP
  - Pushes them toward the Pineapple
##### 5. Modular Framework
  - Install modules for:
     - Phishing portals
     - Credential harvesting
    - DNS spoofing
    - Traffic logging
##### 6. Web-Based Management Ul
   - Easy-to-use dashboard
   - Remote management capability
#### Basic Attack Workflow
1. Power on Pineapple
2. Connect via web Ul
3. Enable Recon mode
4. Start PineAP (Karma engine)
5. Launch beauth attack (optional)
6. Capture connections
7. Analyze traffic / credentials
###### Advantages
  - Plug-and-play compared to manual tools 
   - No complex setup like Kali + adapters
   - Integrated attack framework
  - Highly portable
###### Limitations
   - Expensive compared to USB adapters
   - Limited customization vs full Kali Linux
  - Some attacks ineffective against:
       - WPA3
	 - Proper certificate validation (HTTPS)
## Wireless Network Interface Cards (WNICS)
- A Wireless Network Interface Card (WNIC) is a hardware component that enables a system to connect to wireless networks. In penetration testing, the capabilities of the wireless card-especially support for monitor mode and packet injection-are critical
#### Operating Modes
 - A wireless network interface can operate in three primary modes:
##### 1. Managed Mode
   - Default operating mode
  - Connects to a specific Access Point (AP)
 - Used for normal network communication (internet access)
##### 2. Promiscuous Mode
  - Captures all packets within a network segment
  - Primarily relevant for wired networks
  - Limited use in wireless testing without monitor mode
##### 3. Monitor Mode
  - Allows capturing all wireless traffic in the air
 - Not restricted to a single network
 - Essential for:
    - Packet capture
    -  WPA/WPA2 handshake collection
    - Deauthentication attacks
    - Wireless reconnaissance
#### Identifying Network Interfaces
   Use the following commands to identify available interfaces and hardware:
   - List PCI devices
     - cmd :- lspci
 - List USB devices (external adapters)
    -  cmd :-  lsusb
 - Display network interfaces (deprecated)
    - cmd :-  ifconfig
 - Display wireless interface details
    - cmd :-   iwconfig
 - Modern alternatives:
    - cmd :-  ip link
    - cmd :-  iw dev
#### Enabling Monitor Mode (Manual Method)
- Bring interface down
    - cmd :-  ifconfig wlan0 down
- Verify mode
     - cmd :-  iwconfig wlan0
- Set monitor mode  
     - cmd : - iwconfig wlan0 mode monitor
- Bring interface up
    - cmd :-  ifconfig wlan0 up
- Verify mode
    - cmd :-  iwconfig wlan0
#####  Reverting to Managed Mode
  - Bring interface down
	 -  ifconfig wlan0 down
- Set managed mode
	- iwconfig wlan0 mode managed
-  Bring interface up
    - ifconfig wlan0 up
##### MAC Address Manipulation
   Changing the MAC address can help with:
  - Anonymity
  - Bypassing MAC filtering
  - Avoiding device tracking
#### Using macchanger
- Help menu
    - cmd :-  macchanger -h
- Assign random MAC address
    - cmd :- macchanger -r wlan0
 -  Reset to original MAC
    - cmd :-   macchanger -p wlan0
 - Show current MAC address
    - cmd :-  macchanger -s wlan0
 - Set specific MAC address
    - macchanger -m 58:a0:23:dd:a3:12 wlan0
    - macchanger -mac-58:20:23:dd:a3:09 wlan0
- Using ifconfig (Manual Method)