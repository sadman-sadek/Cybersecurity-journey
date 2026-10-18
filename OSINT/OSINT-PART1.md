# 🕵️‍♂️ Ultimate OSINT & Google Dorking Master Resource Directory (2026 Edition)

A highly structured, up-to-date, and comprehensive reference guide for Cybersecurity Researchers, Defensive Security Analysts, and Ethical Hackers. This document compiles industry-standard tools, frameworks, databases, and advanced Google Dorking techniques to facilitate extensive open-source intelligence gathering.

---

## 🌐 1. Domain Enumeration & Subdomain Discovery
Crucial for mapping an organization's digital attack surface, discovering hidden hosts, and mapping live infrastructure.

| Tool / Website | Type | Description | Primary Resource Link |
| :--- | :--- | :--- | :--- |
| **Subfinder** | CLI Tool | High-speed, passive subdomain discovery tool utilizing curated upstream APIs. | [GitHub Repository](https://github.com/projectdiscovery/subfinder "Subfinder GitHub") |
| **Amass** | CLI Tool | The gold standard for in-depth network mapping, active/passive DNS enumeration, and ASN mapping. | [GitHub Repository](https://github.com/owasp-amass/amass "OWASP Amass GitHub") |
| **DNSDumpster** | Web App | A legendary research platform providing comprehensive DNS records and interactive visual topology maps. | [DNSDumpster Platform](https://dnsdumpster.com "DNSDumpster Site") |
| **crt.sh** | Web App | Searches distributed Certificate Transparency (CT) logs to uncover historically registered subdomains. | [crt.sh Log Database](https://crt.sh "crt.sh Certificate Search") |
| **SecurityTrails** | Web / API | Enterprise-grade platform tracking historical DNS records, WHOIS data, and active subdomain tracking. | [SecurityTrails Engine](https://securitytrails.com "SecurityTrails Platform") |
| **theHarvester** | CLI Tool | A classic Python reconnaissance tool designed to scrape emails, subdomains, names, and open ports from public engines. | [GitHub Repository](https://github.com/laramies/theHarvester "theHarvester GitHub") |
| **PureDNS** | CLI Tool | Fast DNS resolver and subdomain bruteforcing utility capable of accurately filtering out wildcard DNS records. | [GitHub Repository](https://github.com/d3mondev/puredns "PureDNS GitHub") |

---

## 👥 2. People Search & Identity OSINT
Utilized to track digital footprints, cross-reference usernames, and aggregate public registry information.

| Tool / Website | Type | Description | Primary Resource Link |
| :--- | :--- | :--- | :--- |
| **Sherlock** | CLI Tool | Scans a targeted username across over 400 major social networks simultaneously to map user accounts. | [GitHub Repository](https://github.com/sherlock-project/sherlock "Sherlock GitHub") |
| **Epieos** | Web App | Analyzes Google accounts and email addresses to reveal hidden user profiles, reviews, and maps activity. | [Epieos OSINT Portal](https://epieos.com "Epieos Tool") |
| **WhatsMyName** | Web App | Clean web interface and underlying database for identifying profile availability by username handles. | [WhatsMyName App](https://whatsmyname.app "WhatsMyName Web") |
| **OSINT Industries** | Web App | Modern intelligence tool mapping email addresses and phone numbers to active live social media infrastructure. | [OSINT Industries Engine](https://osintindustries.com "OSINT Industries Site") |
| **Social Links** | Software | Advanced intelligence platform supplying open-source investigative modules for blockchain, social, and dark web data. | [Social Links Portal](https://sociallinks.io "Social Links Portal") |
| ** CyberBackgroundChecks** | Web App | Aggregates public US records, listing locations, phone numbers, relatives, and historical contact info. | [CyberBackgroundChecks Site](https://www.cyberbackgroundchecks.com "CyberBackgroundChecks") |

---

## 🔍 3. Infrastructure, Cloud & IoT Search Engines
Engines specifically crawling internet-facing servers, routers, open network ports, industrial controls, and cloud storage buckets.

| Tool / Website | Type | Description | Primary Resource Link |
| :--- | :--- | :--- | :--- |
| **Shodan** | Web / API | The world's first search engine for internet-connected IoT devices, cameras, control systems, and open ports. | [Shodan Platform](https://www.shodan.io "Shodan Search Engine") |
| **Censys** | Web App | Real-time global internet scanning engine facilitating attack surface tracking and asset discovery. | [Censys Search](https://censys.io "Censys Attack Surface") |
| **FOFA** | Web App | Cyber-space asset mapping engine specializing in identifying global network nodes and component vulnerabilities. | [FOFA Search Engine](https://fofa.info "FOFA Asset Search") |
| **BuiltWith** | Web App | Uncovers the underlying technological stack (CMS, CDNs, widgets, frameworks) running on any targeted site. | [BuiltWith Technology Lookup](https://builtwith.com "BuiltWith Tech Lookup") |
| **Grayhat Warfare** | Web App | Dedicated public directory allowing investigators to search exposed and unsecured public AWS S3 buckets. | [Grayhat Warfare Portal](https://buckets.grayhatwarfare.com "Grayhat Warfare") |

---

## 📧 4. Email, Breach & Password Leak Investigation
Crucial for validating corporate email schemes and checking whether accounts have been compromised in third-party data breaches.

| Tool / Website | Type | Description | Primary Resource Link |
| :--- | :--- | :--- | :--- |
| **Have I Been Pwned?** | Web App | Industry-standard index checking if an email or phone number has been exposed in a verified data breach. | [Have I Been Pwned Portal](https://haveibeenpwned.com "Have I Been Pwned") |
| **Hunter.io** | Web App | Maps out distinct corporate email formats and discovers public-facing email directories for domains. | [Hunter.io Finder](https://hunter.io "Hunter.io Email Finder") |
| **Holehe** | CLI Tool | Checks email registration across hundreds of websites (e.g., Twitter, Instagram) without alerting the target. | [GitHub Repository](https://github.com/megadose/holehe "Holehe GitHub") |
| **Intelligence X** | Web App | Archival search tool retrieving historical records, pastebins, dark web dumps, and data leak archives. | [Intelligence X Archive](https://intelx.io "Intelligence X Archive") |
| **DeHashed** | Web App | Modern search engine for compromised assets, allowing reverse-lookups on IPs, hashes, usernames, and leaks. | [DeHashed Portal](https://www.dehashed.com "DeHashed Engine") |

---

## 🗺️ 5. Frameworks, Visual Tools & Resource Repositories
Comprehensive aggregators mapping the vast ecosystem of OSINT utilities and visually charting relational links.

| Tool / Website | Type | Description | Primary Resource Link |
| :--- | :--- | :--- | :--- |
| **OSINT Framework** | Web Directory | An iconic, structured mindmap classifying OSINT tools by data category (email, ip, phone, social). | [OSINT Framework Tree](https://osintframework.com "OSINT Framework Site") |
| **Maltego** | Desktop App | Advanced link-analysis software used to graphically visualize links between nodes (people, domains, infrastructure). | [Maltego Platform](https://www.maltego.com "Maltego Platform") |
| **Spiderfoot** | CLI / Web | High-powered reconnaissance automation platform integrating hundreds of data modules for sweeping scans. | [Spiderfoot Automation](https://www.spiderfoot.net "Spiderfoot Automation") |
| **IntelTechniques** | Web Tools | Curated open investigative resources, customized search forms, and documentation by specialist Michael Bazzell. | [IntelTechniques Hub](https://inteltechniques.com "IntelTechniques Tools") |
| **Awesome OSINT** | GitHub List | Collaboratively curated catalog containing a massive index of active OSINT applications and plugins. | [GitHub Repository](https://github.com/jivoi/awesome-osint "Awesome OSINT GitHub") |

---

## 🧠 6. Advanced Google Dorking (Google Hacking) Manual
Google Dorking utilizes specialized search operators to query the index for highly specific indices, misconfigured servers, and exposed documentation.

### Core Google Dorking Operators

| Operator | Syntax | Purpose | Tactical Usage Example |
| :--- | :--- | :--- | :--- |
| **site:** | `site:target.com` | Restricts results explicitly to the specified domain or top-level domain. | `site:gov "confidential"` |
| **filetype:** | `filetype:pdf` | Isolates documents matching a particular extension (pdf, xlsx, docx, txt, sql). | `site:target.com filetype:sql` |
| **intitle:** | `intitle:"index of"` | Forces Google to only return pages with the query terms inside the HTML page title. | `intitle:"index of /admin"` |
| **inurl:** | `inurl:backup` | Searches for specific keywords present anywhere inside the uniform resource locator string. | `site:target.com inurl:wp-content` |
| **intext:** | `intext:"password"` | Scrapes the visible textual body of webpages for targeted strings, bypassing titles/URLs. | `filetype:log intext:"connection established"` |
| **cache:** | `cache:target.com` | Renders the historical snapshot cached by Google spider bots rather than hitting the live host. | `cache:example.com` |

### Threat Hunting & Investigative Dork Combinations

* **Exposed Administrative Portals & Login Interfaces:**
  ```text
  site:*.target.com inurl:login | inurl:admin | inurl:dashboard
  ```
* **Locating SQL Database Leaks and Backups:**
  ```text
  site:target.com filetype:sql | filetype:db | filetype:backup | filetype:bak
  ```
* **Exposed Apache/Nginx Directory Listings (File Trees):**
  ```text
  intitle:"index of /" inurl:admin | backups | configuration
  ```
* **Discovering Unsecured Corporate PDF, Excel, and Configuration Files:**
  ```text
  site:target.com (filetype:pdf | filetype:xlsx | filetype:docx | filetype:env) "confidential"
  ```
* **Finding Active Log Files Containing Runtime Errors or Connection Strings:**
  ```text
  site:target.com filetype:log "error" | "password" | "database"
  ```

---

🛡️ **Operational Security (OPSEC) Note:** When conducting aggressive Google Dorking or OSINT investigations, always utilize a strictly isolated browser environment, dedicated investigative sock puppets (fake research accounts), and high-quality VPN/Tor loops to prevent leaking your real IP to the target's passive traffic analyzers.
