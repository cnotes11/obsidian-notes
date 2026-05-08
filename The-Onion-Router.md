## Tor (The Onion Router)
- Tor is a privacy-focused network that helps you browse the internet anonymously by routing your traffic through multiple encrypted layers.
##### How Tor Works
   Instead of connecting directly to a website, Tor sends your traffic through a chain of random servers (nodes):
 1. Entry Node - knows your IP, but not your destination
2. Middle Relay - passes encrypted data
3. Exit Node connects to the final website, but doesn't know who you are
- Each layer is encrypted- like peeling an onion
##### Key Features
  - Anonymity: Hides your real IP address
  - Encryption: Multiple layers of encryption
  - Decentralized: Run by volunteers worldwide
  - Access to hidden services: .onion websites
##### Tor vs Normal Internet
| Feature       | Normal Browser | Tor       |
| ------------- | -------------- | --------- |
| IP Visibility | Visible        | Hidden    |
| Speed         | Fast           | Slow      |
| Privacy       | Low            | High      |
| Tracking      | Easy           | Difficult |
##### How to Use Tor
  - Download Tor Browser
  - Install and connect
  - Start browsing anonymously
##### Important Safety Tips
  - Don't log into personal accounts (breaks anonymity)
  - Avoid downloading unknown files
  - Don't use regular browser alongside Tor for sensitive activity
  - Use HTTPS websites whenever possible
##### Limitations
  - Slower browsing speed
  - Some websites block Tor users
  - Exit nodes can see unencrypted traffic
  - Not 100% anonymous if misused
### History of Tor (The Onion Router)
   Tor wasn't originally created by hackers - it actually started as a government research project.
##### Origins (1990s)
- Developed in the mid-1990s by researchers at the United States Naval Research Laboratory
##### Key Contributors
  - Paul Syverson
  - Michael G. Reed
  - David Goldschlag
##### Goal
  - Protect government communications
  - Enable anonymous intelligence gathering online
###### This is where the concept of Onion Routing was invented.
##### Public Release (Early 2000s)
  - 2002 Tor released as open-source software
  - 2004 Publicly funded and expanded
##### Why make it public?
  - More users = more anonymity
  - Larger network = harder to track users
##### Why make it public?
  - More users = more anonymity
  - Larger network = harder to track users
### Tor Project Formation (2006)
   The Tor Project was established
##### Key Figure
  - Roger Dingledine
##### Purpose
  - Maintain and develop Tor
  - Promote privacy and freedom online
## Tor Setup (Linux)
  Install Tor
  -  apt install tor
  Start/Restart Tor service
  -  systemctl restart tor
 Check listening ports
  -  netstat -nltup
 Filter Tor process
  - netstat -nltup | grep tor
Check service status
   -  systemctl status tor
Expected:
1 127.0.0.1:9050 → Tor SOCKS Proxy
## Tor Browser Installation
 - apt install torbrowser-launcher
  - torbrowser-launcher
##### Useful Resources
  - The Hidden Wiki :- https://thehiddenwiki.org/
  - Tails OS :- https://tails.boum.org/index.en.html
 - Ahmia Search :- https://ahmia.fi/
 - Onion Browser :- https://onionbrowser.com/
##### Disclaimer
  - Accessing some onion sites may be illegal depending on jurisdiction
  - Always follow local laws and ethical practices
  - Use Tor responsibly