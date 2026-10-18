# OSINT & Reconnaissance Tools Directory

A curated list of Open Source Intelligence (OSINT) and Reconnaissance tools, platforms, and databases based on your collection, including their core functionalities and how they are utilized in security analysis.

---

## 1. Bitrix24 (`bitrix24.net` / `bitrix24.com`)
* **What it is:** A corporate CRM and cloud collaboration platform used by organizations to manage internal operations, projects, and communications.
* **Core Functions:** Manages employee collaboration, customer data, sales records, internal tasks, and project documents.
* **How Hackers/Analysts Use It:** 
  * **Subdomain Enumeration:** Using tools like `subfinder` or `amass` to find target company subdomains under `*.bitrix24.net`.
  * **Google Dorking:** Finding misconfigured, publicly exposed internal portal data or employee lists.
  * **Target Profiling & Phishing:** Gathering corporate names/emails for highly convincing spear-phishing campaigns.

## 2. Crunchbase (`crunchbase.com`)
* **What it is:** A comprehensive business database platform tracking private/public market companies and investment intelligence.
* **Core Functions:** Displays company funding rounds, investment amounts, corporate leadership structures, and technological indicators.
* **How Hackers/Analysts Use It:**
  * **C-Suite Targeting:** Identifying founders, CEOs, and IT decision-makers to map the organizational hierarchy.
  * **Social Engineering:** Leveraging recent financial developments or massive investments mentioned in the platform to design highly trusted phishing baits.
  * **Supply Chain Mapping:** Tracking a company's third-party vendors, partners, or acquisitions to uncover weaker security links.

## 3. SearchDNS / Netcraft (`searchdns.netcraft.com`)
* **What it is:** An internet monitoring and web-security analysis tool provided by Netcraft.
* **Core Functions:** Discovers subdomains, visualizes domain histories, identifies hosting providers, and detects technologies used on a web server.
* **How Hackers/Analysts Use It:**
  * **Attack Surface Mapping:** Finding forgotten or legacy subdomains that might lack modern security patches.
  * **Hosting Provider Identification:** Pinpointing exactly where a site is hosted to prepare infrastructure-specific test setups.

## 4. Security for Everyone (`securityforeveryone.com`)
* **What it is:** An online automated scanner tool designed to test websites for public-facing infrastructure vulnerabilities.
* **Core Functions:** Scans for SSL/TLS misconfigurations, open ports, outdated software components, and web app bugs.
* **How Hackers/Analysts Use It:**
  * **Quick Reconnaissance:** Finding instantaneous, low-hanging security flaws on public domains without needing complex command-line scanners.
  * **Vulnerability Verification:** Validating whether an identified server port or service contains widely exploitable configurations.

## 5. BuzzSumo (`buzzsumo.com`)
* **What it is:** A content marketing and social media analytics platform.
* **Core Functions:** Tracks viral content, calculates social media engagement metrics, and identifies top digital influencers.
* **How Hackers/Analysts Use It:**
  * **Digital Footprint Analysis:** Monitoring a company's PR campaigns, viral posts, and active brand topics to look for communication trends.
  * **Pretexting & Social Engineering:** Analyzing an executive's highly shared content or writing style to craft matching, tailored social engineering messages.

## 6. Social Searcher (`social-searcher.com`)
* **What it is:** A real-time search engine dedicated to tracking mentions across multiple public social media networks.
* **Core Functions:** Aggregates posts, hashtags, user accounts, and sentiment analysis from various social media sites without requiring user logins.
* **How Hackers/Analysts Use It:**
  * **Employee OSINT:** Monitoring what target employees are posting publicly on platforms regarding internal corporate tools, systems, or locations.
  * **Leak Detection:** Scanning for accidental exposure of proprietary information, source codes, or badge pictures shared by staff.

## 7. Grabify (`grabify.link`)
* **What it is:** A widely known advanced URL shortener and online IP logger.
* **Core Functions:** Generates tracking links that secretly log the IP address, browser user-agent, device specifications, and location data of anyone who clicks it.
* **How Hackers/Analysts Use It:**
  * **Target Identification / De-anonymization:** Tricking a target into clicking a link to discover their actual public IP address and ISP details.
  * **Pre-Attack Verification:** Verifying whether a target is using an active VPN, proxy, or specific mobile device operating system before launching a payload.

## 8. BGP HE (`bgp.he.net`)
* **What it is:** Hurricane Electric's comprehensive BGP (Border Gateway Protocol) toolkit and network internet routing portal.
* **Core Functions:** Provides detailed routing data, Autonomous System Numbers (ASN), IP block ranges, and DNS records for major internet service networks.
* **How Hackers/Analysts Use It:**
  * **Network Range Mapping:** Discovering the entire block of public IP addresses (CIDR ranges) owned by a large target company.
  * **ASN Enumeration:** Uncovering connected infrastructure and upstream ISPs to map the global structural footprint of an enterprise.

## 9. IPInfo (`ipinfo.io`)
* **What it is:** A robust, developer-friendly IP address data API and intelligence database platform.
* **Core Functions:** Reveals geolocations, ASN providers, carrier networks, company ownership, and proxy/VPN flags behind any specific IP address.
* **How Hackers/Analysts Use It:**
  * **Geographical Attribution:** Determining the exact data center, office, or country location hosting a particular asset.
  * **Defense Assessment:** Finding out if a company's web traffic goes through a Content Delivery Network (CDN) like Cloudflare, or directly to their physical servers.

## 10. PeeringDB (`peeringdb.com`)
* **What it is:** A freely accessible, user-maintained database charting network interconnection data and peering points worldwide.
* **Core Functions:** Contains exact physical locations of data centers, Internet Exchange Points (IXPs), network capacities, and structural point details.
* **How Hackers/Analysts Use It:**
  * **Infrastructure Discovery:** Locating the physical facilities, server rooms, or colocation centers where a target houses their primary network routing hardware.
  * **Redundancy Analysis:** Studying target network pathways to assess how they interconnect with other major global telecom providers.

## 11. MXToolbox (`mxtoolbox.com`)
* **What it is:** An online network diagnostics portal focused heavily on email infrastructure and server checks.
* **Core Functions:** Queries MX (Mail Exchange) records, checks DNS parameters, assesses SPF/DKIM/DMARC email security configurations, and audits spam blacklists.
* **How Hackers/Analysts Use It:**
  * **Email Spoofing Assessment:** Checking if a target's SPF/DMARC configurations are weak or missing, which allows hackers to send fake emails pretending to be from that domain.
  * **Mail Server Enumeration:** Identifying the mail provider (e.g., Google Workspace, Microsoft 305) to look for known email portal attack vectors.

## 12. Shodan (`shodan.io`)
* **What it is:** A search engine for internet-connected physical hardware and devices (often called the search engine for the IoT).
* **Core Functions:** Scans the public internet to index open ports, industrial control systems, webcams, servers, routers, and raw service banners.
* **How Hackers/Analysts Use It:**
  * **Port & Service Enumeration:** Finding completely exposed administrative panels, unauthenticated databases (e.g., Elasticsearch, MongoDB), or RDP ports.
  * **Vulnerability Mapping:** Searching for specific old versions of software running on a network that are highly vulnerable to critical public exploits.

## 13. IP Address Guide (`ipaddressguide.com`)
* **What it is:** An online collection of utilities dedicated to basic network protocol parsing and translation tools.
* **Core Functions:** Offers lookup tools for CIDR calculations, IP-to-Decimal conversions, subnet masks, and geolocation data.
* **How Hackers/Analysts Use It:**
  * **Subnet Formatting:** Converting raw IP lists into usable CIDR ranges or specific numeric configurations for input into automated scanners.
  * **Network Structuring:** Verifying network size boundaries during initial footprinting sessions.

## 14. Web-Check (`web-check.xyz`)
* **What it is:** An all-in-one open-source web application designed for comprehensive, single-page passive web architecture recon.
* **Core Functions:** Aggregates DNS records, server locations, SSL certificates, headers, cookies, site technologies, firewalls, and WHOIS information instantly.
* **How Hackers/Analysts Use It:**
  * **Rapid Passive Recon:** Extracting a high-level technical overview of a target web application's design layout without triggering suspicious security logs on their firewall.
  * **Security Header Review:** Quickly checking missing security parameters like CSP, X-Frame-Options, or HSTS.

## 15. ZoomEye (`zoomeye.org`)
* **What it is:** A comprehensive cyberspace mapping search engine, similar to Shodan, powered by Knownsec.
* **Core Functions:** Indexes global web applications, website components, specific active components, operating systems, and network node devices.
* **How Hackers/Analysts Use It:**
  * **Component Fingerprinting:** Searching for specific vulnerable web frameworks (like old WordPress plugins or web servers) across targeted global IP spaces.
  * **IoT Tracking:** Locating routers, IP cameras, or smart devices that contain unpatched software vulnerabilities or factory-default credentials.

## 16. Hunter.how (`hunter.how`)
* **What it is:** An advanced, high-performance cyberspace mapping engine specialized in search queries for asset and threat hunting.
* **Core Functions:** Searches internet-wide asset datasets using complex technical syntax to pinpoint specific open ports, application signatures, and SSL certificates.
* **How Hackers/Analysts Use It:**
  * **Enterprise Asset Discovery:** Tracking down hidden assets, cloud servers, or testing environments owned by a company via SSL certificate organizational fields.
  * **Threat Intel Tracking:** Searching for known signatures or Command & Control (C2) server frameworks exposed on the public web.

## 17. Whoxy (`whoxy.com`)
* **What it is:** An enterprise-grade WHOIS search engine, API service, and domain history archive portal.
* **Core Functions:** Offers massive databases for domain registrations, historic owner records, registrar details, and reverse WHOIS lookups.
* **How Hackers/Analysts Use It:**
  * **Reverse WHOIS Queries:** Searching for an owner's personal name or corporate email address to see every other domain name they have ever registered.
  * **Infrastructure Tracking:** Discovering old, expired, or secondary corporate domains used by target targets that might be completely unprotected.

## 18. VirusTotal (`virustotal.com`)
* **What it is:** A free, crowdsourced platform that aggregates automated file scanning engines, URL checkers, and sandboxes to analyze malware and digital threats.
* **Core Functions:** Analyzes suspicious items with dozens of antivirus engines, maps subdomains, tracks passive DNS records, and logs SSL history.
* **How Hackers/Analysts Use It:**
  * **Subdomain & URL Discovery:** Viewing a massive, passively aggregated list of past subdomains and active URLs registered for a domain name over time.
  * **AV Evasion Check / Recon:** Checking whether past tools, certificates, or assets related to a company have been tagged as malicious or flagged by defenses.

## 19. Nmmapper (`nmmapper.com`)
* **What it is:** An online platform that serves as a web-based frontend interface for popular open-source reconnaissance tools.
* **Core Functions:** Executes remote cloud instances of scanners like Nmap, Sublist3r, WhatWeb, and DNSrecon without setting up a command terminal.
* **How Hackers/Analysts Use It:**
  * **Anonymous Port Scanning:** Scanning a target network from Nmmapper's cloud server IPs, ensuring the analyst's personal IP address stays completely hidden.
  * **Quick Subdomain Enumeration:** Running multiple independent enumeration tools at once to quickly find target interfaces.

## 20. Pentest-Tools (`pentest-tools.com`)
* **What it is:** An advanced cloud-based platform packed with professional-grade penetration testing and vulnerability assessment tools.
* **Core Functions:** Runs remote security audits, advanced network port discovery maps, web structure crawlers, and compiles clean reports on vulnerabilities.
* **How Hackers/Analysts Use It:**
  * **Vulnerability Assessment:** Finding highly exploitable entry pathways such as SQL injections, outdated frameworks, or weak admin configurations remotely.
  * **Target Surface Discovery:** Running highly structured, multi-threaded passive and active scans against target domains seamlessly.

## 21. DNSDumpster (`dnsdumpster.com`)
* **What it is:** A dedicated, free domain research and DNS intelligence gathering analysis web platform.
* **Core Functions:** Discovers subdomains, looks up host records (A, MX, NS, TXT), and automatically creates a visual network topology map of target assets.
* **How Hackers/Analysts Use It:**
  * **Visual Network Mapping:** Getting a clean, graph-based structural look at how a company's internal and external servers are segmented.
  * **Hidden IP Extraction:** Finding backend servers or direct host IPs that may be hiding behind modern protective proxy networks.

## 22. Crt.sh (`crt.sh`)
* **What it is:** A public web-based search dashboard interface for exploring Certificate Transparency (CT) logs.
* **Core Functions:** Tracks and searches every single SSL/TLS certificate ever issued for a domain name by public Certificate Authorities.
* **How Hackers/Analysts Use It:**
  * **Passive Subdomain Enumeration:** Uncovering every historic and active subdomain ever created for a company (even if internal or unindexed by Google) via the certificate logs.
  * **New Asset Tracking:** Spotting newly launched systems or development portals the moment a new SSL certificate is generated for them.

## 23. Subdomain Finder (`subdomainfinder.c99.nl`)
* **What it is:** A specialized, fast online reconnaissance scraper dedicated solely to finding domain names and active subdomains.
* **Core Functions:** Uses a massive internal scanner database and API connections to extract exhaustive lists of child domains.
* **How Hackers/Analysts Use It:**
  * **Attack Surface Discovery:** Spotting unmonitored test structures (`dev.target.com`, `staging.target.com`) that companies often forget to secure.
  * **Asset Enumeration:** Gathering quick, copy-pasteable clean lists of host endpoints to feed into active vulnerability scripts.

## 24. HackerTarget (`hackertarget.com`)
* **What it is:** A comprehensive online suite hosting dozens of high-performance passive and active open-source intelligence tools.
* **Core Functions:** Performs remote fast port scans, reverse IP lookups, DNS sweeps, WHOIS queries, and HTTP header inspections.
* **How Hackers/Analysts Use It:**
  * **Reverse IP Lookup:** Finding out every website sharing the exact same physical server hardware as the target company.
  * **Passive Footprinting:** Using fast, pre-configured queries to map network endpoints safely without establishing noisy connections that trigger alerts.
