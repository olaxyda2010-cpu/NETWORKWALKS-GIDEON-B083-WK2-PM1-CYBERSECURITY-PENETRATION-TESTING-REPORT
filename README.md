# NETWORKWALKS-GIDEON-B083-WK2-PM1-FOOTPRINTING & NETWORK SCANNING PHASES
###
## 👤 Lab Information

| **Field** | **Details** |
|---|---|
| **Pentester Name**<br>*(Cybersecurity Professional)* | **OYEWALE OLAOLUWA GIDEON** |
| **Program/Batch** | B082-Networkwalks |
| **Date** | 17 SEPTEMBER 2026 |
| **Modules Completed** | W2-PM1 (Multiple Kali Tools)<br>W2-PM2 (Zenmap Scanning) |
| **Client/Target** | 1. Networkwalks (secured written permission already)<br>2. My own local LAN Network |
| **Permission secured from client?** | **Yes** |
| **Phases Covered** | **Phase 1:** Reconnaissance & Footprinting<br>**Phase 2:** Scanning & Network Discovery<br>|
###

##1. Introduction
This report documents two Week 2 cybersecurity activities completed as part of my ongoing internship at Networkwalks. The first module focuses on **domain footprinting using multiple Kali Linux tools (W2-PM1)**, while the second covers **local network discovery and scanning with Zenmap (W2-PM5)**.
Together, these exercises demonstrate the progression from **collecting publicly available information about a target to identifying and mapping active hosts within a network**.
All activities were performed using **Kali Linux for the footprinting exercises** and a **Windows PC running Zenmap for the network-scanning exercise**. Each section documents the command or procedure used, the observed output, supporting screenshot evidence, and a brief explanation of the security relevance of each finding.

##2🛠️ Tools Used

The table below lists the tools used in this report and their respective purposes.

| **Tool** | **Purpose** |
|---|---|
| **Kali Linux & Windows** | Operating systems used for reconnaissance and network-scanning activities |
| **WHOIS** | Retrieve domain registration information such as ownership details, registration dates, and name servers |
| **WhatWeb** | Identify web technologies, servers, CMS platforms, plugins, and related information |
| **nslookup** | Resolve domain names to their corresponding IP addresses using DNS |
| **curl -I** | Retrieve and examine HTTP response headers from the target website |
| **WAFW00F** | Identify whether a Web Application Firewall (WAF) is protecting the website |
| **dnsrecon** | Enumerate DNS records including NS, MX, SPF, TXT, and SRV records |
| **Zenmap (Nmap GUI)** | Discover live hosts, open ports, and network information on the local subnet |
| **Windows CMD** | Identify local IP address and MAC address information |

####
# 3. Activities Performed

## 3.1 Footprinting & Reconnaissance

During the reconnaissance stage, I conducted a passive assessment of the **networkwalks.com** domain using six Kali Linux tools: **WHOIS, WhatWeb, Nslookup, cURL, Wafw00f, and DNSRecon**. Each tool was used to examine a different aspect of the target's publicly accessible infrastructure.
I started with 
##
# WHOIS 
**WHOIS** is used to gather publicly available domain registration information and determine the name servers associated with the domain. This provided useful information about the domain's registration and DNS infrastructure.

###
<img width="1366" height="640" alt="image" src="https://github.com/user-attachments/assets/1a225842-0ff1-45c5-8c75-7c1fa64053e6" />
<img width="1045" height="620" alt="image" src="https://github.com/user-attachments/assets/634d76eb-6261-45d3-a35c-354883025efd" />
<img width="1061" height="656" alt="image" src="https://github.com/user-attachments/assets/6e9e0a2d-c699-47ab-86f0-4129e4ca9a5e" />



###
# WHATWEB
Next, I used **WhatWeb** to fingerprint the technologies powering the website. The results revealed the use of **WordPress 7.0.4** and **WP Download Manager 3.3.58**, as well as other technology-related information exposed by the website.

<img width="1366" height="368" alt="image" src="https://github.com/user-attachments/assets/9af390d9-3985-4f04-a8ea-f5804e7b579f" />

###
# NSLOOKUP
I then performed a DNS lookup with **Nslookup** to determine the IP address associated with the domain. The result resolved **networkwalks.com** to **192.232.216.135**
<img width="1366" height="294" alt="image" src="https://github.com/user-attachments/assets/6b10eb93-f232-4e84-babe-fdb6851d8886" />


###

# CURL -I

I then used **cURL** with the `-I` option to examine the website's HTTP response headers. The output revealed additional information about the web application, including the presence of the WordPress REST API endpoint `/wp-json/`.
<img width="1353" height="259" alt="curl -i" src="https://github.com/user-attachments/assets/28322a83-8e94-40e2-983b-58a5e084e11d" />




###
# WAFW00F
Next, I ran **Wafw00f** to identify whether a Web Application Firewall (WAF) was deployed in front of the website. The results indicated the presence of **ModSecurity (SpiderLabs)**.
<img width="1366" height="544" alt="image" src="https://github.com/user-attachments/assets/7a88526b-f7e0-40b0-a643-af209ccfca04" />



###
#DNSRECON
Finally, I used **DNSRecon** to gather available DNS information associated with the domain. The enumeration revealed details related to **name servers, mail servers, SPF/TXT records, service records, and DNS software**.
<img width="1366" height="414" alt="image" src="https://github.com/user-attachments/assets/d4bb62c1-4821-4b40-b956-26b9a65252d1" />


These findings provided additional visibility into the target's **web-server configuration, security controls, and DNS infrastructure**, contributing to the overall reconnaissance profile.
