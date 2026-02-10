## 5. Use Browser Developer Tools
- Open Developer Tools in your browser (usually F12).
-  Go to the Network tab.
-  Reload the page 
- Inspect resource headers and look for CDN clues in the Response Headers or Remote Address fields.
## 6. Use BuiltWith or Wappalyzer 
 - https://builtwith.com/
 - https://www.wappalyzer.com/
 These tool can detect  CDN  usage  along  with other technologies
## Summary

|**Method**|**What to Look For**|
|---|---|
|**CDN Finder Tools**|Direct confirmation of CDN usage|
|**HTTP Headers**|CDN-specific headers like `cf-cache-status`|
|**DNS Records**|CNAMEs pointing to known CDN domains|
|**IP Lookup**|IP belongs to CDN provider|
|**Browser Dev Tools**|Network tab shows cached or edge locations|
|**BuiltWith/Wappalyzer**|Technology stack info including CDN|
# CDN-Bypass-Techniques-Concepts
## CDN Bypass - Techniques & Concepts
   CDN (Content Delivery Network) is used to:
  - Cache content close to users
  - Mask the origin server's IP
  - Provide security features (WAF, rate-limiting, DDoS protection)
CDN Bypass refers to techniques used to:
  - Discover the origin server IP
  - Interact directly with the backend server, bypassing CDN protections
## Common CDN Bypass Techniques
### 1. Find the Origin IP
  - Use recon tools to locate the real IP behind the CDN.
#### a. DNS History / Passive DNS
   Check historical A records before CDN was used:
   - https://securitytrails.com/
   - https://viewdns.info/iphistory/
#### b. Subdomain Enumeration
  - Some subdomains may not be behind the CDN:
#### command:- amass enum -d target.com
#### c. Shodan / Censys Search
  - Search by SSL cert, favicon hash, or headers:
#### command:- ssl.cert.subject.CN:"target.com"
#### command:- http.favicon.hash:123456789
  - https://www.shodan.io/
  - https://censys.com/
#### d. Email/Webmail Leaks
   Check email headers (e.g., password reset) which might reveal origin IP.
#### e. Misconfigured DNS
   Sometimes origin domain points directly to server IP (e.g., ftp.target.com).
#### f. SSL Certificate Transparency Logs
   View issued certificates to discover hidden subdomains:
  - https://crt.sh/
   - https://sslmate.com/certspotter/?utm_source=chatgpt.com
### 2. Test IP Candidates
   Once you have potential origin IPs:
  - Use curl or nmap with Host header:
#### Command:-  curl -Host: target.com" http://<origin_ip>
   If it returns the real site origin IP found.
### 3. Check Firewall Misconfigurations
   Misconfigured origin may accept direct traffic:
  - iptables or fail2ban not properly restricting to CDN IPs
  - Use tools like wafw00f to detect WAF presence/absence
#### command:-  wafweef http://target.com
### 4. Leaked Files or Git Repos
   Sometimes .git, env, or server files are exposed via other subdomains that bypass CDN.
## Defense Tips (For Blue Team)
  - Restrict origin IP to only accept traffic from CDN IP ranges (e.g., Cloudflare IP list)
  - Use firewall rules and allow-lists
  - Monitor DNS records for leaks
  - Regularly scan for exposed services and old records  
# IP-Address-to-Location
   To determine the approximate geographical location of an IP address, you can use online IP geolocation services. These services rely on IP-to-location databases to map an IP address to a country, region, city, and related network details.
## Online IP Geolocation Tools
  - The following web-based tools are commonly used for IP address geolocation lookups:

|**Tool**|**Description**|**URL**|
|---|---|---|
|**IPLocation.net**|Aggregates results from multiple geolocation providers|[https://www.iplocation.net/](https://www.iplocation.net/)|
|**IPLocation.com**|Provides detailed IP geolocation and ISP data|[https://iplocation.com/](https://iplocation.com/)|
|**KeyCDN IP Geolocation Tool**|Fast IP-to-location lookup with ASN and ISP info|[https://tools.keycdn.com/geo](https://tools.keycdn.com/geo)|
|**IPinfo.io**|Popular API-based IP intelligence platform|[https://ipinfo.io/](https://ipinfo.io/)|

## How It Works
  - These tools use IP geolocation databases built from:
    - Regional Internet Registries (ARIN, RIPE, APNIC, LACNIC, AFRINIC)
    - Internet Service Providers (ISPs)
    - Network routing and ASN data
- Typical information returned includes:
    - City
    - Region/State
    - Country
    - Latitude and Longitude (approximate)
    - ISP/Organization
    - ASN (Autonomous System Number)
# Autonomous System (AS/ASN/IP) Lookup
   Autonomous Systems (AS) are large networks or groups of IP prefixes under the control of a single organization that presents a common routing policy to the internet.
## What Can You Look Up?
  - ASN (Autonomous System Number): A unique number(, A515169) assigned to each AS
  - AS Name/Organization: The organization that owns the ASN
  - IP to ASN: Identify the ASN responsible for a given IP address.
  - ASN to IP Ranger View all IP ranges (CIDR blocks) announced by an ASN.
## Online Tools for AS/ASN/IP Lookup

|**Tool**|**Description**|**URL**|
|---|---|---|
|**bgp.he.net**|Detailed ASN info, prefixes, peers|[https://bgp.he.net](https://bgp.he.net/)|
|**IPInfo**|IP -> ASN, org, country, location|[https://ipinfo.io](https://ipinfo.io/)|
|**CIDR Report**|ASN -> prefix list, aggregation|[https://www.cidr-report.org](https://www.cidr-report.org/)|
|**RIPEstat**|RIPE NCC IP/ASN lookup, graph, history|[https://stat.ripe.net](https://stat.ripe.net/)|
|**ViewDNS**|ASN -> organization, IP range|[https://viewdns.info/asnlookup](https://viewdns.info/asnlookup)|
|**Ultratools**|ASN / IP Whois, owner lookup|[https://www.ultratools.com/tools/asnInfo](https://www.google.com/search?q=https://www.ultratools.com/tools/asnInfo)|
|**Hurricane Electric Whois**|Whois, prefixes, peerings|[https://bgp.he.net](https://bgp.he.net/)|
|**Whois (Linux command)**|Local ASN / IP lookup|`whois <IP or ASN>`|
|**Team Cymru**|Command-line ASN lookup|See below|
## Command Line ASN/IP Lookup
### 1. Using whois
#### Command:- whois 8.8.8.8
 - Displays ASN, organization, and contact details
#### Command:- whois A515169
### 2. Using Team Cymru for IP → ASN
#### Install whois if not available:
#### Command:- apt install whois
#### Single IP lookup:
#### Commnad:- whois -h whois.cymru.com-v 8.8.8.8
#### Bulk lookup (replace with your IP list):
#### Command:- whois -h whois.cymru.com -v (your ip list)"
## Sample Output for 8.8.8.8
| **AS** | **IP**  | **BGP Prefix** | **CC** | **Registry** | **Allocated** | **AS Name**             |
| ------ | ------- | -------------- | ------ | ------------ | ------------- | ----------------------- |
| 15169  | 8.8.8.8 | 8.8.8.0/24     | US     | arin         | 1992-12-01    | GOOGLE - Google LLC, US |
# IP Traceroute Tool
  - Traceroute is a diagnostic tool used to track the path that a pocket takes from a source host to a destination IP or domain. It helps identify delays, routing loops, and points of failure in the network
## How Traceroute Works
  - Traceroute sends packets with incrementally increasing Time-To-Live (TTL) values. Each router that handles the packet decreases the TTL by 1. When TTL reaches 0, the router returns a "Time Exceeded" message, revealing its P
## Common Traceroute Tools
| **Tool**              | **Description**                         | **Platform**   |
| --------------------- | --------------------------------------- | -------------- |
| **traceroute**        | Default traceroute tool on Linux        | Linux          |
| **tracert**           | Traceroute command on Windows           | Windows        |
| **mtr**               | Combines traceroute and ping            | Linux          |
| **nmap --traceroute** | Traceroute integrated into network scan | Cross-platform |
| **tcptraceroute**     | Uses TCP instead of ICMP/UDP            | Linux          |
| **tracepath**         | Lightweight alternative to traceroute   | Linux          |
## Example Commands
 -  Linux (traceroute)
#### Command:- traceroute google.com
  - Windows (tracert)
#### Command:-  tracert google.com
  - MTR (Live route and latency statistics)
#### Command:- apt install mtr
#### Command:- mtr google.com
  - TCP Traceroute (for filtered ICMP)
#### Command:- tcptraceroute google.com 80
  - Tracepath
####Command:-  apt install iputils-tracepath
#### Command:- tracepath google.com
## Traceroute Tool Comparison
  - Traceroute and its variants are used to trace the path packets take to reach a destination. Below is a comparison of the most common tools.
## Comparison Table
| **Tool**          | **Platform** | **Protocol Used**                     | **Default Port** | **Features**                                                | **Use Case**                                        |
| ----------------- | ------------ | ------------------------------------- | ---------------- | ----------------------------------------------------------- | --------------------------------------------------- |
| **traceroute**    | Linux/Unix   | UDP (default), ICMP or TCP (optional) | >33434           | Classic traceroute, customizable, shows per-hop details     | General-purpose path tracing on Linux               |
| **tracert**       | Windows      | ICMP Echo                             | ICMP             | Basic built-in traceroute, no port options                  | Quick path check on Windows                         |
| **mtr**           | Linux        | ICMP (or UDP)                         | ICMP             | Real-time traceroute + ping, shows packet loss & latency    | Live network diagnostics and performance monitoring |
| **tcptraceroute** | Linux        | TCP SYN                               | Any (e.g., 80)   | Useful for firewall-bypassed traceroute using TCP handshake | Trace paths to web servers behind ICMP/UDP filters  |
| **tracepath**     | Linux        | UDP                                   | Random           | Lightweight, no root needed, auto MTU detection             | Simple tracing without installing extra tools       |
## Key Differences
### 1. traceroute
  - Protocol: UDP (default), can be ICMP/TCP with flags
  - Port Range: 33434-33534
  - Pros: Flexible, widely supported
  - Cons: Requires root for some options
### Default: UDP
  - Sends UDP packets to high-numbered ports (starting at 33434).
#### Command:-  traceroute example.com
### Use ICMP Instead of UDP
  - -I tells traceroute to use ICMP Echo (like tracert on Windows).
  - Good for tracing networks that block UDP but allow ICMP.
####  Command:- 1 traceroute I example.com
### Use TCP Instead of UDP
  - -T uses TCP SYN packets.
  - Useful to trace through firewalls that block ICMP/UDP but allow TCP (e.g., port 80/443).
  - Requires sudo .
You can also specify the destination TCP port (default is 80):
#### Command:- sudo traceroute -T example.com
####  Command:- sudo traceroute -T -p 443 example.com
## Other Useful Options
| **Option** | **Description**                  |
| ---------- | -------------------------------- |
| -n         | Don't resolve hostnames (faster) |
| -w         | Wait time for replies            |
| -q         | Number of queries per hop        |
| -m         | Max hops                         |
- Example: Trace via TCP Port 443 (HTTPS)
#### Command:-  sudo traceroute -T -p 443 -n google.com
### 2. tracert (Windows)
  - Protocol: ICMP Echo Request
  - Port: ICMP (no port)
  - Pros: Built-in on Windows
  - Cons: Less configurable, no packet loss or jitter metrics
#### Command:- tracert example.com
### 3. mtr
  - Protocol: ICMP (or UDP with udp)
  - Pros: Combines ping + traceroute, real-time, loss & latency per hop
  - Cons: May not be installed by default
#### Command:-  mtr example.com
### 4. tcptraceroute
  - Protocol: TCP SYN packets
  - Use Case: Bypass ICMP/UDP-blocking firewalls
  - Pros: Can simulate browser-like traffic to port 80/443
  - Cons: Requires root, not always pre-installed
#### Command:- sudo tcptraceroute example.com 80
### 5. tracepath
  - Protocol: UDP
  - Pros: No root needed, MTU path discovery
  - Cons: Minimal output, less detailed
#### Command:- tracepath example.com
## Recommendation Based on Use
| **Scenario**                 | **Recommended Tool** |
| ---------------------------- | -------------------- |
| General Linux tracing        | **traceroute**       |
| Windows diagnostics          | **tracert**          |
| Real-time network analysis   | **mtr**              |
| Bypass firewall filters      | **tcptraceroute**    |
| Lightweight non-root tracing | **tracepath**        |
## Online Traceroute Tools

|**Tool**|**URL**|
|---|---|
|**GRC DNS Traceroute**|[https://www.grc.com/dns/traceroute.htm](https://www.google.com/search?q=https://www.grc.com/dns/traceroute.htm)|
|**Ping.eu**|[https://ping.eu/traceroute](https://ping.eu/traceroute)|
|**DNS Checker**|[https://dnschecker.org/ip-traceroute.php](https://www.google.com/search?q=https://dnschecker.org/ip-traceroute.php)|
|**T1 Shopper**|[https://www.t1shopper.com/tools/trace-route/](https://www.google.com/search?q=https://www.t1shopper.com/tools/trace-route/)|
|**YouGetSignal**|[https://www.yougetsignal.com/tools/visual-tracert/](https://www.yougetsignal.com/tools/visual-tracert/)|
Some Output (Linux)
$ traceroute google.com
1  192.168.1.1 (192.168.1.1)  1.123 ms  0.982 ms  1.074 ms
2  100.72.96.1 (100.72.96.1)  9.241 ms  9.238 ms  9.230 ms
3  172.217.163.110 (172.217.163.110)  25.647 ms  25.648 ms  25.649 ms
## Notes
  - ICMP/UDP filtering by firewalls can block standard traceroute responses.
  - TCP-based traceroute is useful for bypassing ICMP filtering (e.g., via port 80).
  - MTR is more dynamic and shows live latency/less per hop.
# IP Address History
   Tools that show the historical IP address records (A records) a domain has pointed to.
## ViewDNS IP History
  - Website: https://viewdns.info/iphistory/
### Lookup Example
 - For domain: https://viewdns.info/iphistory/?domain=armourinfosec.com
1. Domain: armourinfosec.com
2. IP Address History:
3. 
4. - 103.21.59.29          First Seen: 2023-05-12    Last Seen: 2024-11-20  
5. - 162.241.123.20      First Seen: 2022-01-05    Last Seen: 2023-05-11
6.  - 192.185.129.4       First Seen: 2020-08-18    Last Seen: 2022-01-04
  [ Dates represent when ViewDNS first and last observed the domain resolving to each IP,
### Use Cases
  - Investigating past hosting providers
  - Detecting domain hijacking or infrastructure changes
  - Attribution in security research
  - Reconnaissance in penetration testing and OSINT
### Additional Tools for IP History
| **Tool**                  | **Purpose**                                |
| ------------------------- | ------------------------------------------ |
| **SecurityTrails**        | Domain, IP, and DNS history                |
| **DNSDumpster**           | Passive DNS data and subdomain discovery   |
| **ViewDNS Whois History** | Domain ownership and registration timeline |
| **RiskIQ**                | IP resolutions and asset history           |
# Reverse-IP-Add-Domain-Lookup
## Reverse IP Domain Lookup
  - Reverse IP lookup reveals which domains are hosted on a specific IP address. This is useful in OSINT, penetration testing, and infrastructure mapping.
### Use Cases
  - Discover other domains sharing the same web server
  - Identify shared hosting or misconfigured virtual hosts
  - Uncover staging, development, or internal sites
  - Pivot to related targets during reconnaissance or bug bounty hunting
### Online Tools
   You GetSignal-Reverse IP Lookup
   -  https://www.yougetsignal.com/tools/web-sites-on-web-server/
      - Free and simple tool
     - Lists other domains hosted on the same IP
     - Useful for shared or VPS hosting environments
### Security Trails
  - https://securitytrails.com/
    - Premium passive DNS and historical data
    - Shows domain-to-IP associations over time
    - Provides subdomains, WHOIS, and DNS history
### Example Use
- 1. Identify the target IP:
#### Command:-  dig +short example.com
- 2. Perform a reverse IP lookup using:
   - https://www.yougetsignal.com/tools/web-sites-on-web-server/
   - https://securitytrails.com/
### Notes
   - Shared hosting environments may return hundreds of domains per IP
   - Dedicated IP addresses often resolve to a single domain
   - Cloud and CDN providers (e.g., Cloudflare) usually return many unrelated domains
### Defensive Tip
  - Use dedicated IP addresses or properly configured virtual hosts
  - Consider CDN or WAF services to mask the origin IP
# Reverse Name Server Lookup
  - Reverse Name Server (NS) Lookup identifies all domains that use a specific name server. It is useful for enumerating related domains, shared hosting infrastructure, and mapping an organization's digital footprint.
### What It Does
   Given a domain's NS (Name Server) record, reverse lookup tools list other domains using the same name server. This is useful for:
   - Finding other domains hosted with the same provider
   - Discovering sub-brands, development or staging environments, or related assets
   - Pivoting from one domain to others during OSINT or bug bounty research
### How to Find NS Records
#### Using dig
##### Command:- dig armourinfosec.com 115
#### Using nslookup
##### Command :- nslookup-type-ns armourinfosec.com
   This typically returns name servers such as:
1. ns1.hostingprovider.com
2. ns2.hostingprovider.com
## Online Tool
### ViewDNS-Reverse NS Lookup
  - https://viewdns.info/reversens/?nsc/
     - Enter an MX hostname or IP address
     - Returns all domains using that MX server
     - Useful for shared email services (for example, Google Workspace or Microsoft 365)
### Example
  - If armourinfosec.com uses:
##### Command:-  mx1.hostingprovider.com (IP: 192.0.2.10)
   
   A reverse MX lookup might reveal:	
 1.  companyl.com
 2. marketingagency.org
 3. dev-clientsite.net
### Defense Tips
  - Use private or dedicated mail infrastructure
  - Hide internal MX records behind email relays or secure gateways
  - Minimize unnecessary domain exposure through DNS configuration
# Reverse Mail Server Lookup
  - Reverse Mail Server Lookup is used to identify domains that share the same mail (MX) server. This is useful for infrastructure mapping, OSINT, and discovering related domains.
## What It Does
  - Given a domain's MX record, reverse lookup tools reveal other domains using the same mail server (for example, the same IP address or hostname).
## Use Cases
  - Discover organizations hosted on the same email infrastructure
  - Detect multi-tenant or shared email hosting providers
  - Identify email server misconfigurations or exposure
  - Expand the target surface during reconnaissance
## How to Find MX Records
### Using dig
#### Command:- dig armourinfosec.com mx
### Using nslookup
#### Command :- nslookup -type=mx armourinfosec.com
## Online Tool
### ViewDNS-Reverse MX Lookup
  - https://viewdns.info/reversemx/?mx
    - Enter an MX hostname or IP address
    - Returns all domains using that MX server
    - Useful for shared email services (for example, Google Workspace or Microsoft 365)
## Example
 - If armourinfosec.com uses:
#### Commad :-  mx1.hostingprovider.com (IP: 192.0.2.10)

A reverse MX lookup might reveal:
1.  company1.com
2.  marketingagency.org
3.  dev-clientsite.net
## Defense Tips
  - Use private or dedicated mail infrastructure
  - Hide internal MX records behind email relays or secure gateways
 - Minimize unnecessary domain exposure through DNS configuration
# Open Ports Check
  - An open port check allows you to test whether specific TCP ports on a target IP address or domain are accessible from the internet. This is useful for reconnaissance, troubleshooting, and validating firewall rules.
## Use Cases
  - Identify publicly accessible services (SSH, RDP, FTP, HTTP, etc.)
  - Verify firewall, security group, or NAT configurations
  - Discover potentially vulnerable or misconfigured services
  - Validate port forwarding and external access
## Online Port Scanning Tools
### ViewDNS-Port Scan
   https://viewdns.info/portscan/
   - Basic TCP port scan from an external perspective
   - Useful for testing exposed services
### YouGetSignal-Open Ports Tool
   https://www.yougetsignal.com/tools/open-ports/
   - Fast and simple port scanner
   - Supports checking individual ports (for example, 22, 80, 443)
   - Suitable for quick exposure checks
### DNSChecker-Port Scanner
   https://dnschecker.org/port-scanner.php
 -  Scans multiple TCP ports from multiple geographic locations
  - Useful for validating  global not accessibility
### PortChecker.co
   https://portchecker.cafchecking
  - Checks whether a pert is open on your public IP
 - Helpful testing router or firewall port forwarding
## Common Ports to Test
| **Port** | **Service**   |
| -------- | ------------- |
| **21**   | FTP           |
| **22**   | SSH           |
| **23**   | Telnet        |
| **25**   | SMTP          |
| **53**   | DNS           |
| **80**   | HTTP          |
| **110**  | POP3          |
| **143**  | IMAP          |
| **443**  | HTTPS         |
| **3306** | MySQL         |
| **3389** | RDP (Windows) |
## Defense Tips
   - Close all unnecessary ports at the firewall or security group level
   - Use VPNs or port knocking for sensitive remote services
   - Regularly scan public IP addresses for accidental exposure
   - Monitor logs for unauthorized connection attempts
## CLI Alternative
#### Comaand :- nmap -Pn - p 1-1000 example.com
# SEO (Search Engine Optimization)
   SEO stands for Search Engine Optimization.
     [ It is the practice of optimizing websites to rank higher in search engine results (Google, Bing, DuckDuckGo, etc.) for relevant searches.
  - SEO helps your website get free (organic) traffic by making it easier for search engines to understand, trust, and rank your content.
## How SEO Works
Search engines follow three main steps:
1. Crawl-Discover your web pages
2. Index Store and understand the content
3. Rank-Show the best results based on relevance and quality
   [ SEO improves your website's performance in the ranking stage.
## Types of SEO
### 1. On-Page SEO
   - Optimizations done on your website
    - Keyword optimization
    - High-quality content
    - Title tags & meta descriptions
    - Headings (H1, H2, H3)
    - Internal linking
   - Image optimization
### 2. Off-Page SEO
   - Actions taken outside your website
    - Backlinks from other sites
    - Brand mentions
    - Social sharing (indirect impact)
### 3. Technical SEO
  - Improving technical aspects of your site
    - Fast loading speed
    - Mobile-friendly design
    - HTTPS security
    - Clean URLs
    - XML sitemap
    - Fix crawl and indexing issues
## Example
  - If a user searches:
    "best laptop for programming"
Good SEO helps your page appear on the first page of search results, ideally in the top positions.
## Why SEO Is Important
  - Generates free, long-term traffic
  - Builds trust and credibility
  - Improves user experience
   - Increases conversions over time
## SEO vs Paid Ads
| **SEO**      | **Paid Ads**        |
| ------------ | ------------------- |
| Free traffic | Pay per click       |
| Takes time   | Instant results     |
| Long-lasting | Stops when ads stop |
## Summary
  - SEO is a long-term strategy focused on visibility, quality, and relevance, helping websites attract the right audience without paying for ads.
# How Google Search Bot Works Nowadays (Modern Google Search)
  - Google's search system has evolved far beyond a simple "crawler + keyweds" model. Today, it uses Al-driven systems, real user signals, and advanced rendering to rank pages.
## 1. Crawling (Discovery)
 - Google uses Googlebot to discover pages.
### How pages are found:
  - Links from other websites
  - XML sitemaps
  - Internal links
  - Previously indexed URLs
### Important updates:
  - Googlebot is now evergreen Chromium-based
  - It can crawl JavaScript-heavy websites
  - Crawl budget matters for large sites
## 2. Rendering (JavaScript Execution)
  After crawling HTML, Google:
1. Queues the page
2. Renders it using a headless Chrome browser
3. Executes JavaScript
4. Sees the final DOM (what users actually see)
▲ Poor JS rendering = content may not be indexed properly.
## 3. Indexing (Understanding Content)
  Google analyzes:
  -  Text content
  - Images & alt text
  - Videos
  - Structured data (Schema)
  - Language & location
  - Page layout & UX
### Al systems involved:
  - BERT-Understands context & intent
  - MUM-Multimodal understanding (text, images, languages)
  - Neural matching - Matches meaning, not just keywords
## 4. Ranking (Most Important Part)
   Google uses hundreds of signals, including:
### Core ranking factors (modern):
 - Search intent match
  - Content quality & depth
  - E-E-A-T
    - Experience
    - Expertise
    - Authoritativeness
    - Trustworthiness
 - Page speed (Core Web Vitals)
 - Mobile usability
 - HTTPS security
 - Internal & external links
 - User behavior signals (indirect)
## 5. Helpful Content System
  Google now prioritizes:
  - Content written for humans, not search engines
  - First-hand experience
 - Original insights
    [ SEO spam, Al-generated fluff, and keyword stuffing are demoted.
## 6. Core Updates (Ongoing Re-ranking)
  Google continuously:
  - Re-evaluates-old content
  - Adjusts rankings via Core Updates
  - Rewards freshness when relevant
  - Rankings are never permanent.
## 7. Personalization & Context
  Results depend on:
   - Location
  - Device (mobile/desktop)
  - Language
  - Search history (limited)
  - Query intent (informational, transactional, navigational)
## 8. What Googlebot Does NOT Rely On
  - Meta keywords 
  - Keyword density 
 - Fake backlinks 
 - Traffic bots 
## Simplified Flow
   Discover ---> Crawl ---> Render ---> Index ---> Rank ---> Re-rank
## Key Takeaway
  Modern Google Search is:
  - Al-driven
  - Intent-focused
  - User-first
  - Quality over tricks
# Google Keyword Types
   Google keywords are commonly classified into different types based on search intent, length, match type, SEO strategy, and audience.
## 1. Keyword Types Based on Search Intent
### Informational Keywords
   - Used when the user wants to learn or understand something.
    - Examples:
        - what is sql injection
        - how does csrf work
        - google darks list
### Navigational Keywords
  -  Used to reach a specific website or page.
    - Examples:
        - github yt-dip
        - burp suite autorize extension
        - portswigger academy login
### Transactional Keywords
   - Used when the user intends to buy, download, or take action.
     - Examples:
         - burp suite pro price
        - buy domain name
	    - download kali linux iso
### Commercial Investigation Keywords
  - Used for comparison before making a decision.
    - Examples:
        - best subdomain enumeration tool
         - massdns vs dnsx
        - top bug bounty platforms
## 2. Keyword Types Based on Length
### Short-Tail Keywords
   - 1-2 words
   - High search volume and competition
   - Examples:
     - hacking
     - cybersecurity
### Mid-Tail Keywords
   - 2-3 words
   - Moderate competition
   - Examples:
      - bug bounty
     - web security
### Long-Tail Keywords
  - 4 or more words
  - Low competition and high intent
 - Examples:
     - how to find idor vulnerabilities
     - google dorks for admin panel
## 3. Keyword Types Based on Match Type (SEO / Google Ads)
### Broad Match
  -  Matches related searches.
    - Example:
        -  login page
### Phrase Match
   - Matches the phrase in the same order.
    - Example:
        - "admin login"
### Exact Match
  - Matches the exact keyword meaning.
     - Example:
        - [admin login]
## 4. Keyword Types Based on SEO Strategy
### Primary Keywords
-  Main focus keyword.
    - Example:
        - sql injection
### Secondary Keywords
 - Support the primary keyword.
    - Examples:
        - sql injection example
        - sql injection prevention
### LSI / Semantic Keywords
 - Related or contextual keywords.
    - Examples:
        - database attack
        - parameter tampering
## 5. Keyword Types Based on Audience
### Branded Keywords
  - Contain brand names.
     - Examples:
        - PortSwigger
        - Burp Suite
### Non-Branded Keywords 
 - Generic keywords without brand names.
    - Examples:
        -  web vulnerability scanner 
### Geo-Targeted Keywords 
  - Include location.
     - Examples: 
         - bug bounty india
	      -  cybersecurity course delhi 
## 6. Special Keyword Types
### Question-Based Keywords
 - Examples:
    - what is xss
    - how to exploit idor
### Evergreen Keywords
   Always relevant.
   - Examples:
    - password security
### Trending Keywords
   Time-sensitive keywords.
   - Examples:
      - latest zero day vulnerability
## Summary Table
| **Category**   | **Types**                                              |
| -------------- | ------------------------------------------------------ |
| **Intent**     | Informational, Navigational, Transactional, Commercial |
| **Length**     | Short-tail, Mid-tail, Long-tail                        |
| **Match Type** | Broad, Phrase, Exact                                   |
| **SEO**        | Primary, Secondary, LSI                                |
| **Audience**   | Branded, Non-branded, Geo                              |
| **Special**    | Question-based, Evergreen, Trending                    |
# Google-Hacking-Database
## Google Hacking Database (GHDB) & Google Dorks
 - Google Dorking (or Google Hacking) uses advanced Google search operators to discover publicly accessible sensitive data, configuration files, or vulnerabilities. This technique is widely used in cybersecurity, OSINT, penetration testing, and digital forensics.
## What Is the Google Hacking Database (GHDB)?
 - The Google Hacking Database (GHDB) is a repository of crafted Google search queries (a.k.a. Google Dorks) used to identify:
     - Exposed credentials
    - Open directories
    - Webcams and admin portals
    - Backup/config files
    - Database dumps
[GHDB GitHub Mirror: readloud/Google-Hacking-Database?
## Use Cases
### Information Gathering
  - Locate login portals, config files, or directories
  - Discover hidden or forgotten content.
### Open Source Intelligence (OSINT)
   - Identify leaks related to organizations or people.
  - Extract emails, usernames, phone numbers.
### Penetration Testing
  - Find known vulnerabilities via exposed panels or default pages.
  - Enumerate possible attack surfaces.
### Bug Bounty Hunting
  - Discover exposed dev/staging environments.
  - Check for misconfigured S3 buckets, Git directories, etc.
## Why It Matters
  - Proactive Defense: Helps sysadmins identify leaks before attackers do.
  - Threat Intelligence: Aids red teaming and incident response teams.
  - Security Awareness: Organizations become more vigilant about exposure.
## Types of Google Search Operators
  - Google Search Operators can be classified into two main categories:
### Google Search Basic Operators
  - These basic search operators help refine Google queries and improve search accuracy. Ideal for both casual and technical users.
#### + (Force Inclusion)
   [ A Deprecated: No longer supported in modern Google Search, but historically used to force inclusion of a term.
  - Purpose: Ensure a specific keyword is included in results.
  - Example:
    -  cybersecurity +training
   Ensures that the word "training" appears in the results.
#### - (Exclude Term)
  - Purpose: Exclude specific words from search results.
  - Example:
    - cybersecurity -training
   Omits any results containing the word "training."
#### ~ (Suggest Similar Terms)
   [ A Deprecated: May not work reliably in current search behavior.
 - Purpose: Search for synonyms and related terms.
  - Example:
     - ~hacking
   Returns results for hacking, security, penetration testing, etc.
#### .. (Search Within a Range)
  - Purpose: Search within a numeric range (years, prices, versions, etc.).
  - Example:
    - cybersecurity trends 2015.. 2023
   Finds results referencing years 2015 to 2023.
#### * (Wildcard)
  - Purpose: Acts as a placeholder for unknown or variable words.
  - Example:
     -  best security tools *
   Matches results like "best web security tools", "best cloud security tools", etc.
#### "" (Exact Match)
  - Purpose: Search for an exact word or phrase.
  - Example:
    -  "penetration testing guide"
   Only returns pages with the exact phrase inside quotes.
#### OR (Logical Operator)
 - Purpose: Matches either one term or another
    - Example:
        - malware OR virus
## Google Search Advanced Operators
 - Advanced operators allow precise targeting of search queries and are commonly used in cybersecurity, OSINT, bug bounty, and forensic investigations.
## Search Rules
##### 1. No Space Between Operator and Term
  - Operators must be directly attached to keywords
     - Correct: intitle: armourinfosec
     - Incorrect: intitle: armourinfosec
##### 2. Case Insensitivity
 - Google searches are not case-sensitive
      - intitle: CyberSecurity =  intitle:cybersecurity
##### 3. Handling Multi-word Terms
 - Use double quotes or dots
    - intitle: "Ethical Hacking"
    - inurl: ethical.hacking.tutorial
##### 4. Combining Operators
  - Multiple operators can be chained for precision
     - site:github.com intitle: "README" intext:"api_key"
## Key Advance Operator
| **Operator**    | **Description**                  | **Example**                             |
| --------------- | -------------------------------- | --------------------------------------- |
| **intitle:**    | Term appears in page title       | `intitle:"cybersecurity training"`      |
| **allintitle:** | All terms must be in title       | `allintitle:"cybersecurity training"`   |
| **inurl:**      | Term appears in URL              | `inurl:cybersecurity-training`          |
| **allinurl:**   | All terms must be in URL         | `allinurl:cybersecurity training`       |
| **intext:**     | Term appears in body text        | `intext:"penetration testing"`          |
| **filetype:**   | Searches specific file types     | `filetype:pdf "cybersecurity training"` |
| **ext:**        | File extension filter            | `ext:ppt "cybersecurity training"`      |
| **site:**       | Restricts results to a domain    | `site:armourinfosec.com`                |
| **inanchor:**   | Anchor text search               | `inanchor:armourinfosec`                |
| **link:**       | Pages linking to a URL (limited) | `link:armourinfosec.com`                |
| **cache:**      | Google cached version            | `cache:armourinfosec.com`               |
| **related:**    | Similar websites                 | `related:google.com`                    |
| **info:**       | Information about a URL          | `info:armourinfosec.com`                |
Example Queries Using  ext: Operator

| **Extension** | **Purpose**       | **Example**                               |
| ------------- | ----------------- | ----------------------------------------- |
| **ext:pdf**   | PDF documents     | `ext:pdf "ethical hacking tutorial"`      |
| **ext:ppt**   | PowerPoint slides | `ext:ppt "cybersecurity training"`        |
| **ext:doc**   | Word documents    | `ext:doc "penetration testing report"`    |
| **ext:xls**   | Excel sheets      | `ext:xls "vulnerability assessment data"` |
| **ext:txt**   | Text files        | `ext:txt "password list"`                 |
## Popular Google Dork Patterns
| **Purpose**           | **Dork Example**                     |
| --------------------- | ------------------------------------ |
| Exposed Login Pages   | `inurl:admin login`                  |
| Directory Listing     | `"index of /" site:example.com`      |
| Configuration Files   | `ext:env`                            |
| Database Dumps        | `filetype:sql "insert into" -github` |
| Logs with Credentials | `filetype:log intext:password`       |
| Exposed Cameras       | `inurl:view/view.shtml`              |
| Search Within Site    | `site:example.com confidential`      |
| PDF Discovery         | `filetype:pdf "internal use only"`   |
| Public Git Repos      | `inurl:.git -github`                 |
| Backup Files          | `ext:bak`                            |
## Example Scenarios
### Find Webcams
  -  inurl:view/view.shtml
### Discover Exposed.env Files
  - filetype:env intext:DB_PASSWORD
### Locate Login Pages
  - inurl:admin inurl:login | intitle:"admin panel"
### Search Confidential PDFs
  - filetype:pdf "confidential" site:example.com
## Warning and Legal Note
   - Google Dorking must only be used for ethical and authorized purposes.
    - Do: Audit your own assets or participate in authorized bug bounty programs.
    - Do Not: Access unauthorized systems or private data
#####  Improper usage may violate:
  - Search engine Terms of Service
  - Local and international laws (e.g., CFAA, IT Act 2000)
## Additional Resources
 - Exploit-DB GHDB: https://www.exploit-db.com/google-hacking-database
 - GitHub GHDB Mirror: https://github.com/readloud/Google-Hacking-Database
 - OSINT Framework: https://osintframework.com/
# Google Dorks - Exploit Search Techniques
  - The following are powerful Google Dork queries used to locate exposed directories, files, services, credentials, subdomains, and more. These are typically used for ethical hacking, OSINT, and reconnaissance.
    [ Source: https://www.exploit-db.com/google-hacking-database
## Exposed Credentials and Secrets
 - Searches for .env files that often contain secrets like API keys or database credentials.
     - inurl:.eny DB PASSWORD
 - Locates JSON files with possible API keys.
    - filetype: son intext:api_key
- Searches for ini files containing DB configurations.
    - filetype:ini intext:db_user
 - Targets YAML config files with credentials.
    -  filetype: yaml intext:password
- Searches for AWS keys in source code.
    - intext: "AWS SECRET ACCESS KEY
## Technology & Framework Detection
- Finds WordPress admin panels.
    - inurl:wp-admin
 - Searches for exposed Laravel debug pages.
    - inurl:/_ignition/ intitle:"Laravel"
 - Finds Django error pages which can leak debug info.
    - intitle: "OperationalError at" inurl:/admin/
 - Locates Magento admin login pages.
    - inurl:admin/login site:*.* -demo 
- Targets exposed .git folders.
    - intitle: "Index of /.git"
## Login Panels & Access Portals
-  General login portals:
    -  intitle:"Login Page" inurl:login
- Admin login pages:
    - intitle:"admin login"
 -  CPanel login panels:    
    - inurl:cpanel filetype:php
- Remote desktop logins:
     - intitle: "Remote Web Workplace"
- Router/web Ul logins:
    - intitle: "Router setup" OR intitle:"web interface login"
##  Misconfigurations & Debug Info
 - PHP info pages:
     - inurl:phpinfo.php
 - Apache default pages:
    - intitle:"Apache2 Ubuntu Default Page"
 - Jenkins dashboard:
    -  intitle: "Dashboard [Jenkins]"
 - Kibana dashboard exposed:
     - intitle: "Kibana" inurl:/app/kibana
 - Exposed.DS_Store files:
     - intitle: "Index of" ".DS_Store"
##  Log, Backup, and Database Files
-   Searches for log files with debug output:
    -  filetype:log intext: "Exception"
- Finds SQL backups:
     -  filetype:sql "dump" OR "backup"
 - Locates .bak database backups:
    - filetype:hak intext: "CREATE TABLE
- ZIP and RAR archives labeled as config or backup:
    -  filetype:zip OR filetype:rar "config" OR "backup"
## Error Messages and Stack Traces
 - Java exceptions:
    - intext:"java.lang.NullPointerException"
 - PHP errors: 
    - intext: "Fatal error" filetype:php
- MySQL errors:
    - intext: "You have an error in your SQL syntax"
- ASP.NET stack trace:
    - intext: "System.Web.HttpException" filetype:aspx
##  Publicly Accessible Services and Devices
- Open webcams:
     -  inurl:view/index.shtml
- VNC portals:
     - intitle: "VNC viewer for Java"
- JIRA dashboards:
     - intitle:"Dashboard - JTRA "
- GitLab web interface:
     - intitle:"Sign in .  GitLab"
##  Source Code Exposure
 - Exposed.env
     - inurl:.env intext: "DB PASSWORD"
 - Exposed config.php:
    -  inurl:config.php intext:mysql_connect
- Source code files:
    -  filetype:php OR filetype:asp OR filetype:js "password"
- GitHub gists with passwords:
     - site:github.com intext:password
##  OSINT & Recon
 - Company email leaks:
      - intext:"@company.com" filetype:xls OR filetype:csv
 - Phone numbers & contact info:
     - intext:"contact" AND "phone" site:example.com
 - Job portals with internal tools or tech stack:
     - site:careers.example.com intext:"developer"
## More Examples      
   - 1 intitle:"index of" filetype: ini
- Searches for YAML configuration files.
    -  intitle:"index of" filetype:yaml OR filetype:yml
- Finds shell script files in open directories.
    - intitle:"index of" filetype:sh "script"
- Searches for .txt files that may contain leaked usernames and passwords for Gmail accounts.
    -  filetype:txt username password @gmail.com
- Targets.txt files with potential login credentials for Hotmail users.
     - filetype:txt username password @hotmail.com
- Finds leaked Yahoo email account details stored in .txt files.
     - filetype:txt username password @yahoo.com
- Locates plaintext credentials associated with Ymail accounts.
     -  filetype:txt username password @ymail.com
- Searches for Rediffmail user credentials in .txt format.
    -  filetype:txt username password @rediffmail.com
- Targets Facebook-associated accounts listed in .txt dumps.
    -  filetype:txt username password @facebook.com
- Searches for Gmail credentials in Excel spreadsheets.
    - filetype:xle рассмоrd @gmail.com	
# Google Hacking Database Tools
- These tools automate Google Dorking and enhance reconnaissance using search engines like Google, Bing, Yahoo, and others. They are widely used in OSINT, bug bounty, and penetration testing.
## pagodo (Passive Google Dork)
 Description:
  - Automates the process of querying the https://www.exploit-db.com/google-hacking-database(GHDB) using Google search. Useful for identifying sensitive files, directories, or configuration leaks.
### Example Usage:
  python3 pagodo.py-g dorks.txt -s armourinfosec.com
  - -g dorks.txt: File containing Google dorks
   - -s armourinfosec.com: Target domain
## theHarvester
Description:
  -  A powerful tool for gathering emails, subdomains, hosts, and employee names using public sources like Google, Bing, Baidu, and more.
### Example: Scan a domain with Google
- theHarvester -d armourinfosec.com -l 500 -b google
### Example: Scan Facebook
 theHarvester -d facebook.com -l  500 -b google
- -d: Domain to search
- -l : Number of results to fetch
- -b: Search engine backend (google, bing, duckduckgo, etc.)
## metagoofil
   Metadata harvester to extract usernames, software versions, and more from publicly available documents (PDF, DOCX, PPTX, etc.).
### Example Usage:
   metagoofil -d armourinfosec.org -l 20 -t pdf -n 20 -f report.html -o doc
   - -d: Domain to search
   - -l: Number of Google results to process
   - -t: File type (e.g., pdf, docx, ppt)
   - -n: Number of files to download
   - -f: Output HTML report file
   - -o: Output directory for downloaded documents
## Summary
| **Tool**         | **Purpose**                                     | **Notes**                         |
| ---------------- | ----------------------------------------------- | --------------------------------- |
| **pagodo**       | Run GHDB dorks against domains                  | Passive enumeration, customizable |
| **theHarvester** | Email & subdomain harvesting via search engines | Supports multiple engines         |
| **metagoofil**   | Metadata extraction from public documents       | Finds usernames, OS info, tools   |
# Shodan Recon
   - Shodan is a search engine for internet-connected devices. It's widely used in cybersecurity for reconnaissance, identifying exposed systems, services, and potential vulnerabilities.
  - Website: https://www.shodan.io/
  - Filter Reference: https://www.shodan.io/search/filtersc
## How Shodan Works
### 1. Global Internet Scanning
   Shodan uses a large network of scanners to connect to every public IPv4 address and tries to interact with open ports. It behaves like a banner grabber.
For example:
 - It connects to x.x.x.x:80 and records the HTTP response header.
- It connects to x.x.x.x:21 and records the FTP banner.
### 2. Banner Collection
   When Shodan connects to a device or service, it retrieves the service banner or metadata that the service exposes. This may include:
   - Software name and version (e.g., Apache 2.4.7)
   - OS type and version
   - SSL certificate details
   - Web server headers
   - Authentication methods
   - Error messages
   - Custom titles or messages
### 3. Indexing and Tagging
  - Collected data is:
    - Indexed in a search database
     - Tagged by:
          - Port (port:80)
         - Protocol (product: "Apache")
         - Organization (org: "Google")
         - Location (country: US)
         - Vulnerabilities (using banner signature + known CVES)
         - SSL certificate fields
        - Web technologies(http.component: "WordPress")
### 4. Vulnerability Matching
   Shodan cross-references collected banners with known CVEs from:
   - https://nvd.nist.gov/
   -  Internal vulnerability signature sets
   If a match is found, the system flags the service with the corresponding vuln: CVE-XXXX-XXXX tag.
### 5. User Interface + API
  -  You can access all this information via:
      - https://webui.me/
- Shodan CLI
     - https://developer.shodan.io/
         - Allows automation and integrations
         - Common in red team tools and threat intelligence
## Example of Data for an IP on Port 80:
{
   "ip_str": "192.0.2.123",
   "port": 80,
   "org": "Example ISP",
   "location": {
     "country_name": "India",
     "city": "Delhi"
   },
   "http": {
     "title": "Apache2 Ubuntu Default Page",
     "server": "Apache/2.4.18 (Ubuntu)"
   },
   "os": "Linux",
   "vulns": ["CVE-2017-5638"]
 }
## table 
## Account Setup

1. Register on [Shodan](https://www.shodan.io).
2. Visit your profile to obtain your **API Key**.