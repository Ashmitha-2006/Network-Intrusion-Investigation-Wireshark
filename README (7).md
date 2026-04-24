
# 🔴 SOC INCIDENT INVESTIGATION REPORT

## Network Intrusion Analysis using Wireshark

---

### 📁 Case Details

* **Investigation Type:** Network Traffic Analysis
* **Tool Used:** Wireshark
* **Environment:** Simulated SOC Investigation
* **Analyst:** Dishini Ashmitha
* **Severity:** 🔴 HIGH

---

## 📋 Executive Summary

During network traffic analysis, a single internal host (**10.2.28.88**) was identified exhibiting abnormal communication patterns, including excessive outbound connections, DNS anomalies, and suspicious HTTP activity.

The investigation confirmed multiple **indicators of compromise (IOCs)** such as:

* High-volume external communication
* Repeated failed DNS lookups
* Suspicious HTTP POST requests
* Potential malicious file transfer

These behaviors strongly suggest **possible host compromise**, with characteristics aligned to **malware beaconing and data exfiltration activity**.

---

## 🖥️ Victim Host Identification

### 🔍 How the Host Was Identified

Using:

* **Statistics → Conversations**
* **Statistics → Endpoints**

The host **10.2.28.88** stood out due to:

* Highest packet count
* Communication with multiple external IPs
* Long-duration sessions

---

### 📊 Evidence

#### Suspicious Traffic Patterns

![Conversations](conversations.png)

#### Endpoint Activity Confirmation

![Endpoints](endpoints.png)

---

## 👤 System & User Identification

### 🔍 Extraction Methodology

Victim system details were extracted through protocol-level analysis:

| Protocol | Purpose                  |
| -------- | ------------------------ |
| NBNS     | Hostname identification  |
| Kerberos | Authentication tracking  |
| SAMR     | User account enumeration |

---

### 📌 Evidence

![NBNS](nbns.png)
➡️ Hostname identified from NetBIOS broadcasts

![Kerberos](kerberos.png)
➡️ Authentication activity linked to user sessions

![SAMR](samr.png)
➡️ Full user account details extracted

---

## 🚨 Red Flag #1 – Abnormal Network Behavior

* One internal host communicating with **multiple external endpoints**
* High packet and byte count
* Persistent long-duration connections

📊 Evidence:
![Conversations](conversations.png)

➡️ Indicates:

* Possible **compromised host**
* Potential **command & control (C2) communication**

---

## 🌐 Red Flag #2 – Suspicious DNS Activity

### 🔍 Observations

* Repeated DNS queries
* Multiple **failed lookups ("No such name")**
* Pattern consistent with automated scripts

📊 Evidence:
![DNS](dns.png)

➡️ Interpretation:

* Possible **domain probing**
* Behavior consistent with **malware beaconing**

---

## 🌍 Red Flag #3 – Suspicious HTTP Activity

### 🔍 Observations

* HTTP POST requests to external servers
* Unusual outbound communication patterns

📊 Evidence:
![HTTP](http.png)

➡️ Interpretation:

* Possible **data exfiltration**
* Potential communication with malicious infrastructure

---

## 📂 Red Flag #4 – Suspicious File Transfer

### 🔍 Findings

* Extracted HTTP objects from captured traffic
* Identified suspicious file: **`fakeurl.htm`**

📊 Evidence:
![Export](export.png)

➡️ Interpretation:

* Possible **malware delivery or staging file**
* Indicates compromise lifecycle progression

---

## 📊 Indicators of Compromise (IOCs)

| Type     | Indicator                |
| -------- | ------------------------ |
| Host     | 10.2.28.88               |
| Behavior | High outbound traffic    |
| DNS      | Repeated failed queries  |
| HTTP     | Suspicious POST requests |
| File     | fakeurl.htm              |

---

## 🧠 Threat Assessment

Based on the investigation:

The host **10.2.28.88** is **highly likely compromised**.

### Likely Activities:

* 🔗 Command & Control (C2) communication
* 📤 Data exfiltration via HTTP
* 🤖 Automated malware behavior

---

## 🛡️ Recommended Actions

* Immediately **isolate the affected host**
* Conduct **endpoint forensic analysis**
* Monitor network for **similar traffic patterns**
* Implement **egress filtering and alerting rules**
* Strengthen **endpoint protection mechanisms**

---

## 🔧 Investigation Methodology

1. **Traffic Profiling**

   * Protocol hierarchy and traffic distribution

2. **Host Identification**

   * Endpoint & conversation analysis

3. **DNS Inspection**

   * Identification of anomalous queries

4. **HTTP Analysis**

   * Detection of suspicious outbound traffic

5. **File Extraction**

   * Analysis of transferred objects

6. **User Attribution**

   * Protocol-based identity extraction

---

## 💡 Skills Demonstrated

* Network Traffic Analysis
* Threat Hunting & Detection
* Multi-Protocol Analysis (DNS, HTTP, Kerberos, SMB)
* Incident Investigation & Reporting
* IOC Identification

---

## 🌐 Real-World Relevance

This investigation reflects real **SOC analyst workflows**, including:

* Identifying compromised hosts through behavioral analysis
* Correlating multi-protocol activity
* Detecting early-stage malware communication
* Investigating potential data exfiltration

---

## 🧾 Conclusion

This analysis successfully identified a compromised internal system through multiple indicators, including abnormal traffic behavior, DNS anomalies, suspicious HTTP communication, and file transfer activity.

The investigation demonstrates strong **practical SOC skills**, including traffic analysis, threat detection, and structured incident reporting.

---

## 🔗 Author

**Dishini Ashmitha**


