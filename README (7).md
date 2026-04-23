# 🔍 Network Intrusion Investigation using Wireshark

> A hands-on incident response case study analyzing real network traffic to uncover suspicious behavior, DNS anomalies, C2 communication patterns, and potential data exfiltration.

---

## 📌 Overview

This project simulates a real-world Security Operations Center (SOC) investigation. Using Wireshark, network traffic was analyzed at the packet level to identify a potentially compromised host, trace its communication behavior, and assess the threat it poses to the network.

---

## 🎯 Objectives

- Identify suspicious hosts based on traffic behavior
- Analyze communication patterns across protocols (DNS, HTTP, SMB, Kerberos)
- Detect indicators of compromise (IOCs)
- Investigate potential data exfiltration and C2 activity

---

## 🔬 Investigation Breakdown

### 📊 Suspicious Host Identification
![Conversations](conversations.png)

Host **10.2.28.88** was flagged for communicating with multiple IPs simultaneously, exhibiting long-duration connections and an unusually high packet count — clear indicators of abnormal network behavior.

---

### 📈 Endpoint Analysis
![Endpoints](endpoints.png)

Endpoint statistics confirmed **10.2.28.88** as the most active system on the network by both packet and byte count, warranting deeper investigation.

---

### 🌐 DNS Analysis
![DNS](dns.png)

Repeated DNS queries with multiple failed lookups ("No such name") were detected, suggesting automated domain probing — a common behavior associated with malware beaconing or C2 communication attempts.

---

### 🌍 HTTP Traffic Analysis
![HTTP](http.png)

Suspicious HTTP POST requests were observed communicating with external IPs, raising concerns about malicious downloads or active data exfiltration.

---

### 👤 System & User Identification

| Protocol | Finding |
|----------|---------|
| NBNS | ![NBNS](nbns.png) Hostname of the affected system identified |
| Kerberos | ![Kerberos](kerberos.png) User authentication activity traced |
| SAMR | ![SAMR](samr.png) Full user account details extracted |

---

### 📂 File Extraction
![Export](export.png)

HTTP objects were exported from the captured traffic. A suspicious file — **fakeurl.htm** — was identified, suggesting the host may have downloaded or served malicious content.

---

## 🚨 Key Findings

- **Abnormal outbound communication** — One internal host communicated with an unusually high number of external IPs
- **DNS probing behavior** — Repeated failed DNS lookups consistent with automated malware activity
- **Suspicious HTTP POST requests** — Indicative of data being sent to an external server
- **Suspicious file transfer** — Evidence of potentially malicious file activity via HTTP

---

## 🧠 Threat Assessment

Based on observed traffic patterns, the host **10.2.28.88** is likely compromised. The evidence suggests:

- **Command & Control (C2) communication** with external servers
- **Possible data exfiltration** via HTTP POST requests
- **Automated or scripted behavior** consistent with malware activity

---

## 🛡️ Recommendations

- **Isolate** the affected host immediately to prevent further network communication
- **Conduct forensic analysis** on the system to identify the malware or threat actor
- **Monitor outbound traffic** network-wide for similar behavioral patterns
- **Strengthen endpoint defenses** and enforce stricter egress filtering rules

---

## 🛠️ Tools & Technologies

| Tool | Purpose |
|------|---------|
| Wireshark | Packet capture and traffic analysis |
| DNS Protocol Analysis | Detecting domain probing behavior |
| HTTP Protocol Analysis | Identifying suspicious requests and file transfers |
| Kerberos / NBNS / SAMR | User and host identification |

---

## 💡 Skills Demonstrated

- Network Traffic Analysis & Packet Inspection
- Threat Detection & Behavioral Analysis
- Multi-Protocol Investigation (DNS, HTTP, TCP, SMB, Kerberos)
- Incident Response Documentation & Reporting
- IOC Identification & Threat Assessment

---

## 🌐 Real-World Relevance

The techniques applied in this investigation reflect standard practices used in Security Operations Centers (SOC) globally. The ability to analyze raw network traffic, correlate protocol-level behavior, and identify indicators of compromise is a foundational skill in threat detection and incident response roles.

---

*Conducted as part of a self-directed cybersecurity learning path focused on network forensics and incident response.*
