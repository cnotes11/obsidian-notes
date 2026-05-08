 Proxy-VPNs-and-TOR
- Proxy, VPNs, and TOR are three different technologies used to hide your IP address, improve privacy, or bypass restrictions on the internet. They work in different ways and provide different levels of security. 
## 1. Proxy Servers 
  - A proxy server acts as an intermediary between your device and the internet. When you send a request, it goes to the proxy first, which then forwards it on your behalf.
### How It Works 
   Your Device--> Proxy Server --> Internet
### Types of Proxies
  - HTTP/HTTPS Proxy-Handles web browser traffic only
  - SOCKS5 Proxy-Handles any TCP/UDP traffic; more flexible
  - Transparent Proxy -Often used by ISPs or organizations without your knowledge
  - Reverse Proxy-Sits in front of servers (e.g., Nginx, Cloudflare) to manage load or hide infrastructure 
### Pros & Cons
Pros                     | Cons
------------------------|-------------------------------
Fast and lightweight    | Usually no encryption
Easy to configure       | Provider can see your traffic
Good for geo-bypassing  | Low anonymity
Often free              | Per-app, not system-wide
## 2. VPNs (Virtual Private Networks)
   A VPN encrypts all your device's internet traffic and tunnels it through a server in another location, masking your real IP address.
### How It Works

Your Device [Encrypted Tunnel] <--> VPN Server --> Internet  
### Common Protocols
| Protocol   | Speed     | Security | Use Case        |
|------------|-----------|----------|-----------------|
| WireGuard  | Very Fast | High     | Modern default  |
| OpenVPN    | Medium    | High     | Cross-platform  |
| IKEv2      | Fast      | High     | Mobile devices  |
| L2TP/IPSec | Medium    | Medium   | Legacy support  |
### Pros & Cons
Pros                       | Cons
---------------------------|-------------------------------------
Encrypts all traffic       | Must trust VPN provider
Hides IP system-wide       | Costs money (good ones)
Bypasses censorship        | Can reduce connection speed
Widely supported           | Some services block VPN IPs
## 3. TOR (The Onion Router) 
   TOR routes your traffic through a series of volunteer-operated relays around the world, encrypting it in multiple layers - like layers of an onion at each hop.
###  How It Works 
   Your Device --> Guard Node --> Middle Relay --> Exit Node --> Internet 
 Each node only knows the previous and next hop-no single node knows both who you are and what you're accessing. 
### Key Features 
  - Access to onion sites (dark web) 
  - Run by a non-profit (The Tor Project) 
  - Completely free and open source
  - Traffic encrypted in 3+ layers 
### Pros & Cons
Pros                          | Cons
------------------------------|-----------------------------------------
Strongest anonymity           | Very slow (multiple hops)
No single point of trust      | Exit nodes can see unencrypted traffic
Free to use                   | Blocked by many websites
Access to .onion sites        | Not suitable for streaming
### Side-by-Side Comparison
| Feature          | Proxy               | VPN              | TOR                    |
| ---------------- | ------------------- | ---------------- | ---------------------- |
| Encrypts Traffic | Usually not         | Yes              | Yes                    |
| Hides IP Address | Yes                 | Yes              | Yes                    |
| Anonymity Level  | Low                 | Medium           | High                   |
| Speed            | Fast                | Medium           | Slow                   |
| Trust Required   | Proxy operator      | VPN provider     | No single party        |
| System-wide      | Per-app             | Yes              | Browser only (default) |
| Cost             | Free / Paid         | Usually paid     | Free                   |
| Best For         | Quick geo-bypassing | Everyday privacy | Maximum anonymity      |
## Combining Technologies
  Some users combine these tools for layered protection:
  - VPN + TOR ("Tor over VPN") - Hides Tor usage from your ISP; VPN provider sees you use Tor but not your activity
  - TOR + VPN ("VPN over Tor") - VPN provider cannot see your real IP; more complex to set up
  - VPN + Proxy-Adds an extra IP hop on top of VPN encryption
   
## Proxy-Servers
   A Proxy Server is an intermediary server that forwards requests from a client to another server. Instead of connecting directly to a website, the client sends the request to the proxy server, which then connects to the destination server and returns the response.
### Benefits of Proxy Servers
 - Hide the user's real IP address 
 - Bypass network restrictions or censorship
 - Improve privacy and anonymity
 - Monitor and filter internet traffic
 - Cache content to improve performance
### Common Proxy Server Tools
#### 1. CCProxy (Windows)
   CCProxy is a Windows-based proxy server software used to share internet connections and control network access.
##### Features:
 - HTTP/HTTPS Proxy
 - SOCKS Proxy
 - FTP Proxy
 - User authentication
 -  Internet access control
 - Traffic monitoring
#### 2. Squid Proxy (Linux)
   Squid is a powerful caching proxy server commonly used on Linux systems.
##### Features:
  - HTTP/HTTPS proxy support
  - Web caching to reduce bandwidth usage
  - Access Control Lists (ACL)
  - Authentication support
  - Logging and monitoring
##### Configuration file:
-  /etc/squid/squid.conf
#### 3. PHP-Proxy (Web-based Proxy Script)
   A PHP Proxy is a web-based proxy script that allows users to browse websites through a web interface.
##### Examples:
   - Glype Proxy
   - PHP-Proxy
  - CGIProxy
##### How it works:
1. Upload the proxy script to a web server
2. Open the proxy page in a browser
3. Enter the target website URL
4. The proxy server fetches the page and displays it
##### Advantages:
  - No software installation required
  - Accessible from any browser
  - Can bypass local network restrictions
##### Limitations:
  - Slower than direct connection
  - Some websites block web proxies
  - Limited protocol support
## Public-Proxy-Server-Lists
- https://www.proxynova.com/proxy-server-list/
- http://www.freesafeip.com/
 These websites provide lists of free proxy servers including:
   - IP Address
   - Port
   - Proxy Type (HTTP/SOCKS4/SOCKS5)
  - Country
  - Latency
▲ Free proxies may be unreliable and may log traffic.
### Hide My IP Tools
Example tool:
###### UltraSurf
Download:
 - xhttps://ultrasurf.us/download/
  UltraSurf is commonly used to:
   - Hide IP address
   - Bypass internet censorship
   - Create encrypted proxy tunnels
## ProxyChains Configuration  
### ProxyChains
   ProxyChains is a Linux/Unix tool that forces network connections made by an application to pass through one or more proxy servers. It works by intercepting network calls and redirecting them through SOCKS4, SOCKS5, or HTTP proxies.
   ProxyChains is commonly used in network security testing, anonymity setups, and bypassing network restrictions.
### How ProxyChains Works
ProxyChains uses LD PRELOAD to hook networking functions (such as connect()) used by applications. It intercepts these calls and routes them through configured proxy servers.
##### Traffic Flow
Application --> ProxyChains  --> Proxy Server(s) --> Destination Server
   This allows applications that do not natively support proxies to still use them.
#### Basic Syntax
 - proxychains
##### Example