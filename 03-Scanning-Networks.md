# Module 03: Scanning Networks
## EC-Council Certified Ethical Hacker (CEH) v13

**Category:** Ethical Hacking / Network Security  
**Training Provider:** EC-Council  
**Environment:** Authorized EC-Council Cyber Range  
**Primary Tools:** Nmap, Metasploit Framework, Parrot Security OS

### 1. Overview

Completed hands-on network scanning exercises focused on identifying active hosts, discovering operating systems, and gathering information about network services.

The exercises provided practical experience with network reconnaissance and identifying potential security weaknesses within an authorized lab environment.

### 2. Host Discovery Using Nmap

**Objective:** Identify active devices within a target network.

Technical skills practiced:
- ARP host discovery
- UDP ping scanning
- ICMP Echo scanning
- ICMP ping sweeps across IP ranges
- TCP SYN and ACK discovery techniques
- Identifying live hosts within a subnet

Example commands:

```bash
nmap -sn -PR 10.10.1.22
nmap -sn -PU 10.10.1.22
nmap -sn -PE 10.10.1.22
nmap -sn -PE 10.10.1.10-23
```

### 3. Operating System Discovery

**Objective:** Identify operating systems and system information using Nmap.

Techniques practiced:
- Active OS fingerprinting
- Service and version detection
- Nmap aggressive scanning
- Nmap Scripting Engine (NSE)
- SMB operating system discovery

Example commands:

```bash
nmap -A 10.10.1.22
nmap -O 10.10.1.22
nmap --script smb-os-discovery.nse 10.10.1.22
```

### 4. Network Scanning Using Metasploit

**Objective:** Identify open ports, active hosts, services, and operating system information.

Tools and modules practiced:
- Metasploit Framework
- SYN port scanning
- TCP port scanning
- SMB version identification
- Network service enumeration

Metasploit modules:

```text
auxiliary/scanner/portscan/syn
auxiliary/scanner/portscan/tcp
auxiliary/scanner/smb/smb_version
```

### 5. Technical Skills Developed

- Network reconnaissance
- Host discovery and IP identification
- Port scanning and service enumeration
- OS fingerprinting
- Nmap command-line operations
- Metasploit Framework navigation
- Basic network security assessment
- Understanding potential attack surfaces

### 6. Practical Application

These techniques are useful during authorized security assessments to identify network-connected systems, understand exposed services, and provide information that can support vulnerability assessments.

### 7. Tools & Technologies

| Tool | Purpose |
|---|---|
| Nmap | Network discovery and port scanning |
| Metasploit | Network scanning and security assessment |
| Parrot Security OS | Ethical hacking environment |
| NSE | Automated network information gathering |

### 8. Lab Documentation

This entry summarizes practical exercises completed through EC-Council CEH v13 training.

**Note:** All scanning activities were performed within the authorized EC-Council training environment. No production systems were targeted.
