# Module 04: Enumeration

## Overview
This module covers enumeration techniques used in ethical hacking and penetration testing. The labs focus on identifying network devices, users, shared resources, directory services, and running network services.

**Course:** EC-Council CEH v13  
**Module:** 04 – Enumeration  
**Environment:** EC-Council Cyber Range

## Lab 1: NetBIOS Enumeration

**Objective:** Identify NetBIOS information and network shares using Windows command-line utilities.

**Tools:** Nbtstat, Net use, Windows Command Prompt.

Commands:

```cmd
nbtstat -a 10.10.1.11
nbtstat -c
net use
```

**Key Learning:**
- Identifying remote computer names.
- Reviewing NetBIOS name information.
- Examining network connections and shared resources.

**Lab Question:** Identify the shared folder or drive available on Windows Server 2019.

**Result:** To be documented from the actual lab output.

## Lab 2: SNMP Enumeration

**Objective:** Retrieve network management information using SNMP and SnmpWalk.

**Tools:** SnmpWalk, Parrot Security.

Commands:

```bash
snmpwalk -v1 -c public 10.10.1.22
snmpwalk -v2c -c public 10.10.1.22
```

**Key Learning:**
- Understanding Simple Network Management Protocol (SNMP).
- Identifying SNMP versions.
- Understanding community strings.
- Recognizing risks associated with exposed SNMP information.

**Important Option:** `-c` specifies the SNMP community string.

## Lab 3: LDAP Enumeration

**Objective:** Explore Active Directory information using Active Directory Explorer.

**Tools:** Active Directory Explorer (AD Explorer), LDAP.

**Activities:**
- Connect to the Windows Server 2022 target.
- Explore the Active Directory domain structure.
- Review user accounts and directory attributes.
- Examine user properties, including display names and User Principal Names (UPNs).

**Key Learning:**
- LDAP stands for Lightweight Directory Access Protocol.
- LDAP commonly uses TCP port 389.
- Active Directory organizes information about users, computers, and groups.
- Directory enumeration can expose sensitive organizational information.

**Lab Questions:**
- Identify the Domain Controller IP address.
- Find the `userPrincipalName` for Jason M.

**Results:** To be documented from AD Explorer.

## Lab 4: NFS Enumeration

**Objective:** Identify NFS services and investigate network file-sharing resources.

**Tools:** Nmap, RPCScan, SuperEnum.

Commands:

```bash
nmap -p 2049 10.10.1.19
echo "10.10.1.19" >> Target.txt
./superenum
python3 rpc-scan.py 10.10.1.19 --rpc
```

**Key Learning:**
- NFS stands for Network File System.
- NFS enables file sharing across networks.
- RPCScan identifies RPC services and potential NFS resources.
- SuperEnum automates service enumeration.

**Important Finding:** NFS commonly uses port `2049`.

## Lab 5: DNS Enumeration

**Objective:** Identify DNS information and test whether a DNS server permits zone transfers.

**Tools:** dig, nslookup.

Linux commands:

```bash
dig ns certifiedhacker.com
dig @ns1.bluehost.com certifiedhacker.com axfr
```

Windows commands:

```cmd
nslookup
set querytype=soa
certifiedhacker.com
```

**Key Learning:**
- DNS translates domain names into IP addresses.
- NS records identify authoritative name servers.
- SOA records contain administrative information about a DNS zone.
- AXFR requests a DNS zone transfer.
- Unrestricted zone transfers can expose DNS records.

**Lab Findings:** The provided lab instructions show that the zone transfer was refused.

## Lab 6: SMTP Enumeration

**Objective:** Use Nmap scripts to investigate SMTP users, commands, and relay configurations.

**Tools:** Nmap, Nmap Scripting Engine (NSE).

Commands:

```bash
nmap -p 25 --script=smtp-enum-users 10.10.1.19
nmap -p 25 --script=smtp-open-relay 10.10.1.19
nmap -p 25 --script=smtp-commands 10.10.1.19
```

**Key Learning:**
- SMTP stands for Simple Mail Transfer Protocol.
- TCP port 25 is commonly used for SMTP.
- Nmap scripts can identify possible mail users and supported commands.
- Misconfigured open relays can create email security risks.

**Lab Question:** Record the number of possible mail users returned by Nmap.

## Lab 7: Enumeration Using Global Network Inventory

**Objective:** Collect system configuration and network information using Global Network Inventory.

**Tool:** Global Network Inventory.

**Activities:**
- Configure a single-address scan.
- Target Windows Server 2022 at `10.10.1.22`.
- Run the inventory scan.
- Review system and network information.

**Information Examined:**
- Operating system details.
- BIOS information.
- NetBIOS applications.
- User accounts and groups.
- Running services.
- Installed software.
- Shared folders.
- Hardware information.

**Key Learning:** System inventory tools help security professionals understand system configurations and identify potentially exposed resources.

**Lab Question:** Identify the full operating system name displayed for `10.10.1.22`.

## Lab 8: AI-Assisted Enumeration Using ShellGPT

**Objective:** Explore how AI can assist with generating and executing enumeration commands.

**Tools:** ShellGPT, Parrot Security, Nmap, SnmpWalk, dig.

Example commands:

```bash
sgpt --shell "Perform NetBIOS enumeration on target IP 10.10.1.11"

sgpt --chat enum --shell "Perform SNMP enumeration on target IP 10.10.1.22 using SnmpWalk"

sgpt --chat enum --shell "Perform SMTP enumeration on target IP 10.10.1.19"

sgpt --shell "Perform IPsec enumeration on target IP 10.10.1.22 with Nmap"

sgpt --shell "Scan target IP 10.10.1.22 for SMB services using Nmap"
```

**Key Learning:**
- Using AI to generate command-line instructions.
- Automating repetitive enumeration tasks.
- Reviewing AI-generated commands before execution.
- Verifying AI-generated results using traditional security tools.

**Important Finding:** SMB commonly uses TCP port `445`.

## Technical Skills Developed

- NetBIOS enumeration.
- SNMP enumeration.
- LDAP and Active Directory inspection.
- NFS and RPC enumeration.
- DNS enumeration and zone-transfer testing.
- SMTP service enumeration.
- Network and system inventory.
- AI-assisted enumeration using ShellGPT.
- Identifying network services and potential misconfigurations.

## Tools and Technologies

| Tool | Purpose |
|---|---|
| Nbtstat | NetBIOS enumeration |
| Net use | Network shares and connections |
| SnmpWalk | SNMP enumeration |
| AD Explorer | Active Directory inspection |
| Nmap | Network and service enumeration |
| RPCScan | RPC and NFS enumeration |
| SuperEnum | Automated enumeration |
| dig | DNS queries |
| nslookup | DNS information gathering |
| Global Network Inventory | System inventory |
| ShellGPT | AI-assisted command generation |

## Practical Cybersecurity Relevance

Enumeration helps security professionals understand the information exposed by network systems and identify potential security weaknesses.

These techniques support:
- Network security assessments.
- Active Directory security reviews.
- Network service discovery.
- File-sharing permission audits.
- DNS and SMTP configuration reviews.
- Vulnerability assessments.

## Authorization and Documentation

All exercises are intended for the authorized EC-Council CEH v13 Cyber Range.

Actual results and screenshots should reflect personally performed lab exercises. No unauthorized production systems or networks should be targeted.

**Portfolio Note:** Screenshots, findings, and command outputs should be added as personal evidence after completing each exercise. Never publish passwords, credentials, or AI activation keys.
