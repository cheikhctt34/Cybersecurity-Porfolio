# Module 10: Denial-of-Service (DoS and DDoS)

## Overview

This module covers Denial-of-Service (DoS) and Distributed Denial-of-Service (DDoS) attacks. These attacks attempt to make systems, applications, or network services unavailable to legitimate users by overwhelming their resources with excessive traffic or connection requests.

A DoS attack typically originates from one source, while a DDoS attack uses multiple systems to generate traffic against a target.

The hands-on labs explored attack traffic in a controlled virtual environment and demonstrated methods for detecting and responding to these attacks.

## Learning Objectives

- Understand the differences between DoS and DDoS attacks.
- Identify common DoS and DDoS attack categories.
- Understand how SYN floods, UDP floods, and other traffic floods affect systems.
- Observe suspicious network traffic using Wireshark.
- Monitor system resource usage during simulated attacks.
- Use defensive tools to identify and block suspicious traffic.

## Lab 1: Perform DoS and DDoS Attacks Using Various Techniques

### Lab Overview

This lab demonstrated how multiple systems can generate excessive traffic against a target machine and affect its availability.

**Task 1: DDoS simulation using ISB and UltraDDoS-v2**

- Explored network traffic simulation tools.
- Observed how excessive TCP traffic can affect a target system.
- Used Windows Resource Monitor to observe system performance.
- Examined CPU utilization during simulated traffic activity.

**Task 2: Botnet demonstration**

- Explored how multiple systems can be coordinated in a botnet.
- Learned about command-and-control communication.
- Observed traffic from multiple virtual machines.
- Used Wireshark to inspect network traffic on the Ubuntu victim machine.
- Monitored memory utilization during the simulation.

*Note: These exercises were performed in the authorized CEH virtual lab. Attack execution commands and malware payload instructions are intentionally excluded from this public portfolio.*

### Attack Categories

| Category | Description | Examples |
|---|---|---|
| Volumetric | Consumes available network bandwidth | UDP flood, ICMP flood |
| Protocol | Exhausts network connection resources | SYN flood, ACK flood |
| Application Layer | Overwhelms application resources | HTTP GET/POST flood, Slowloris |

### Tools Used

- ISB (I'm So Bored)
- UltraDDoS-v2
- Metasploit Framework
- Wireshark
- Windows Resource Monitor
- Ubuntu System Monitor

### Knowledge Check

**Question 10.1.1.1:** Which port was targeted during the DoS simulation?

**Answer:** Port 80 (HTTP).

**Question 10.1.2.1:** Which interface was selected on Ubuntu to capture network traffic?

**Answer:** `eth0`.

## Lab 2: Detect and Protect Against DoS and DDoS Attacks

### Lab Overview

This lab focused on identifying suspicious traffic and applying defensive measures to protect a target system.

The exercise used Anti DDoS Guardian to monitor network connections and identify systems generating unusually high traffic.

### Detection Techniques

1. **Activity Profiling:** Monitors normal network traffic patterns and identifies unusual increases in packet activity.
2. **Sequential Change-Point Detection:** Identifies significant changes in traffic patterns over time.
3. **Wavelet-Based Signal Analysis:** Analyzes traffic patterns to identify abnormal behavior.

### Defensive Exercise: Anti DDoS Guardian

The lab demonstrated how to:

- Monitor incoming and outgoing network traffic.
- Identify remote IP addresses generating excessive traffic.
- Inspect individual network sessions.
- Review traffic details and incoming byte counts.
- Use the Block IP feature to block a suspicious source.
- Stop the simulated traffic and verify the defensive response.

### Knowledge Check

**Question 10.2.1.1:** Which Anti DDoS Guardian option can be used to stop an ongoing DoS attack?

**Answer:** `Block IP`.

### Tools Used

| Tool | Purpose |
|---|---|
| Anti DDoS Guardian | Monitor and block suspicious network traffic |
| LOIC | Used in the controlled lab to simulate traffic flooding |
| Wireshark | Capture and analyze network packets |
| Resource Monitor | Monitor CPU and system resource utilization |
| System Monitor | Observe memory and system performance |

## Key Technical Skills Learned

- Understanding DoS and DDoS attack methods.
- Recognizing volumetric, protocol, and application-layer attacks.
- Understanding botnets and command-and-control concepts.
- Monitoring network traffic with Wireshark.
- Identifying suspicious source IP addresses.
- Reviewing CPU and memory utilization during traffic spikes.
- Applying IP-blocking measures to help mitigate malicious traffic.

## Real-World IT and Cybersecurity Application

Understanding DoS and DDoS attacks is important for IT support and cybersecurity teams because service disruptions can affect business operations and customer access.

In an IT Help Desk environment, these skills can help with:

- Recognizing unusual network slowdowns and service interruptions.
- Collecting network and system performance information.
- Escalating suspected attacks to the appropriate security team.
- Providing relevant source IP and traffic information for investigation.
- Understanding how firewalls and DDoS protection services help maintain availability.

## Conclusion

This module provided practical exposure to DoS and DDoS concepts, traffic monitoring, and defensive techniques. It reinforced the importance of identifying abnormal network activity and responding quickly to protect system availability.

**Lab Environment:** EC-Council CEH v13 Virtual Lab

**Module:** 10 – Denial-of-Service

**Focus:** Attack concepts, network traffic analysis, detection, and mitigation.

*All exercises were conducted in an authorized training environment. No real-world systems were targeted.*
