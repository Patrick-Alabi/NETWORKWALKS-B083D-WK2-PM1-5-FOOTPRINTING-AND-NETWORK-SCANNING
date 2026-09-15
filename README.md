# NETWORKWALKS-B083D-WK2-PM1-5-FOOTPRINTING-AND-NETWORK-SCANNING
# Week 2 Cybersecurity Footprinting and Network Scanning Projects

## Overview

This repository documents my Week 2 practical cybersecurity and ethical
hacking, focused on **footprinting, reconnaissance, information
gathering, and network scanning**.

Five practical modules were completed:

1.  Footprinting and reconnaissance with WHOIS, WhatWeb, nslookup, cURL,
    DNSRecon and WAFW00F
2.  Footprinting and reconnaissance with the Google Hacking Database
    (GHDB)
3.  Footprinting with Maltego
4.  Footprinting and reconnaissance with theHarvester
5.  Network scanning with Zenmap/Nmap

The objective was to understand how publicly available information and
network discovery techniques can be used during security assessments,
and how defenders can use the same techniques to identify exposed
information and reduce attack surface.

> **Ethical Use:** These techniques should only be used against systems
> you own, a controlled lab, or systems for which you have explicit
> authorization.

## Learning Objectives

-   Practice passive and active reconnaissance concepts
-   Gather domain and DNS information
-   Fingerprint web technologies
-   Analyze HTTP responses and headers
-   Identify WAF technologies
-   Use Google search operators and GHDB
-   Perform graph-based reconnaissance with Maltego
-   Discover emails and hosts with theHarvester
-   Identify live network hosts with Zenmap/Nmap
-   Review IP and MAC addresses
-   Visualize network topology
-   Document findings and security recommendations

------------------------------------------------------------------------

## Project 1 --- Footprinting & Reconnaissance

### Tools

`whois` • `whatweb` • `nslookup` • `curl` • `wafw00f` • `dnsrecon`

### Activities

The authorized target domain was assessed using publicly available
information. The exercise covered domain registration information, DNS
records, name servers, MX/TXT records, website technology
fingerprinting, HTTP response headers, WAF detection and DNS
enumeration.

### Key Observations

The assessment identified information including domain and registrar
details, IP/DNS relationships, mail records, website technologies and
security-related HTTP headers. WhatWeb identified technologies including
WordPress, Apache, Bootstrap and jQuery, while WAFW00F identified
ModSecurity as the detected WAF.

### Security Relevance

Footprinting shows how much information can be collected before
exploitation is attempted. Defenders can use the same process to
identify unnecessary public information, exposed technologies and
configuration details.

------------------------------------------------------------------------

## Project 2 --- Footprinting with GHDB

### Tools

-   Google Hacking Database (GHDB)
-   Google search operators

### Activities

This module explored how carefully constructed search queries, commonly
called **Google dorks**, can locate information that has already been
indexed and exposed publicly.

Two exercises were completed:

1.  Identifying publicly exposed camera-related results.
2.  Identifying publicly accessible mathematics PDF directory listings.

### Security Relevance

The exercise demonstrated that search engines can expose device
interfaces, directory listings, documents and other resources that
organizations unintentionally make public.

> Direct third-party camera access links are intentionally not
> reproduced in this repository.

------------------------------------------------------------------------

## Project 3 --- Footprinting with Maltego

### Tool

-   Maltego

### Activities

Maltego was installed and configured in a Windows environment. The
practical exercise involved creating a domain entity, using
`networkwalks.com` as the authorized training target, running
email-related transforms and reviewing the resulting reconnaissance
graph.

### Security Relevance

Maltego demonstrates how individual pieces of publicly available
information can be connected into a larger intelligence picture. This
helps security professionals understand relationships between domains,
organizations and other publicly available entities.

------------------------------------------------------------------------

## Project 4 --- Footprinting & Reconnaissance with theHarvester

### Tool

-   theHarvester 4.8.2
-   Kali Linux

Two searches were performed against the training target
`microsoft.com`.

### Task 1 --- Baidu

``` bash
theHarvester -d microsoft.com -l 1000 -b baidu
```

Result:

-   1 email address
-   10 hosts
-   No IPs or people returned

### Task 2 --- Multiple Sources

``` bash
theHarvester -d microsoft.com -l 50 -b all
```

Result:

-   7 email addresses
-   1,312 hosts
-   No IPs or people returned

The multi-source run also demonstrated real-world tool limitations:
several sources required API keys, while others produced connection,
rate-limit or API-related errors.

### Security Relevance

Email addresses and subdomains can contribute to an organization's
attack surface. The exercise reinforced the importance of understanding
what information is publicly discoverable and minimizing unnecessary
exposure.

------------------------------------------------------------------------

## Project 5 --- Network Scanning with Zenmap/Nmap

### Tools

-   Zenmap
-   Nmap
-   Windows Command Prompt

### Activities

The practical exercise covered local IP/subnet identification, Ping
Scan, live-host discovery, MAC-address review and network-topology
visualization.

### Scan Result

The completed scan identified **4 live hosts** on the `10.0.0.0/24`
subnet:

  Host          Status
  ------------- --------
  `10.0.0.1`    Up
  `10.0.0.2`    Up
  `10.0.0.9`    Up
  `10.0.0.10`   Up

The scan covered 256 IP addresses and reported 4 hosts up. The results
also showed virtual network interfaces, including QEMU and Oracle
VirtualBox virtual NICs.

### Security Relevance

Network discovery provides asset visibility. Security teams can compare
discovered hosts against an authorized asset inventory and investigate
unexpected systems.

------------------------------------------------------------------------

## Evidence

The final project report contains screenshots and evidence from the
practical exercises.

Repository structure:

``` text
.
├── README.md
├── W2-PM-Permission-Letter.pdf
├── W2-PM1-5-FINAL-Report.docx
└── zenmap-topology.pdf
```

Screenshots are structured according to the
relevant task.

------------------------------------------------------------------------

## Tools & Technologies

  Area                   Tools
  ---------------------- ------------------------------------
  OSINT / Footprinting   WHOIS, WhatWeb, nslookup, DNSRecon
  Web Reconnaissance     cURL, WAFW00F
  Search-based Recon     GHDB, Google search operators
  Graph Reconnaissance   Maltego
  Email / Host Recon     theHarvester
  Network Scanning       Nmap, Zenmap
  Operating Systems      Kali Linux, Windows

------------------------------------------------------------------------

## Key Takeaways

1.  Reconnaissance is a critical early stage of a security assessment.
2.  Public information can reveal more about an organization than
    expected.
3.  Different reconnaissance tools provide different perspectives.
4.  Search engines can expose information that organizations
    unintentionally make public.
5.  Email addresses and subdomains can increase an organization's attack
    surface.
6.  Network discovery helps defenders maintain visibility of assets.
7.  Reconnaissance findings should be translated into defensive actions.
8.  Authorization and scope are essential when performing security
    testing.

## Defensive Recommendations

-   Regularly review publicly exposed information.
-   Audit DNS records and unnecessary subdomains.
-   Remove sensitive documents and directory listings from public
    access.
-   Review search-engine indexing and unwanted exposure.
-   Minimize unnecessary disclosure of organizational email information.
-   Maintain an accurate inventory of authorized network devices.
-   Review exposed services and interfaces.
-   Keep web applications and security controls properly configured.
-   Perform periodic authorized reconnaissance against organizational
    infrastructure.

## Conclusion

The five projects provided practical exposure to the reconnaissance
phase of cybersecurity assessments.

The work progressed from domain and web footprinting to search-engine
reconnaissance, graph-based intelligence gathering, automated
public-source discovery and local network host discovery.

The overall lesson was that effective cybersecurity begins with
**visibility**. Organizations need to understand what information,
infrastructure and services are visible to others before they can
effectively reduce their attack surface.

## Disclaimer

This repository is intended for **educational and defensive
cybersecurity purposes only**.

The techniques demonstrated here should only be used against systems you
own, in a dedicated laboratory environment, or against systems for which
you have explicit written authorization.

Unauthorized scanning, reconnaissance, access or exploitation may
violate laws, policies and terms of service.

## Author

**Patrick Alabi**\
Cybersecurity Professional --- B083

Week 2 Cybersecurity & Ethical Hacking Practical Projects
