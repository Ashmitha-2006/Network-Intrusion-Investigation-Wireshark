# Network-Intrusion-Investigation-Wireshark 
Wireshark-based  network traffic analysis case study which recognizes suspicious activity, DNS anomalies, and potential data exfiltration
# 🚨 Network Intrusion Investigation using Wireshark

## 🧠 Incident Response Case Study

This project presents a network traffic investigation using Wireshark to identify suspicious activity, abnormal communication patterns, and potential system compromise.

---

## 🎯 Objective

* Identify suspicious hosts in the network
* Analyze communication behavior
* Detect malicious activity
* Investigate potential data exfiltration

---

## 📊 Suspicious Host Identification

![Conversations](conversations.png)

* Identified host **10.2.28.88** communicating with multiple IPs
* Long-duration connections and high packet count observed
* Indicates abnormal network behavior

---

## 📈 Endpoint Analysis

![Endpoints](endpoints.png)

* Host **10.2.28.88** shows highest packet and byte count
* Most active system in the network
* Flagged for further investigation

---

## 🌐 DNS Analysis

![DNS](dns.png)

* Repeated DNS queries detected
* Multiple failed lookups (“No such name”)
* Suggests suspicious or automated domain activity

---

## 🌍 HTTP Traffic Analysis

![HTTP](http.png)

* Suspicious HTTP POST requests identified
* Communication with external IPs observed
* Possible data exfiltration or malicious downloads

---

## 👤 System & User Identification

![NBNS](nbns.png)

* Hostname identified via NBNS

![Kerberos](kerberos.png)

* User authentication observed via Kerberos

![SAMR](samr.png)

* Full user details extracted

---

## 📂 File Extraction

![Export](export.png)

* Extracted HTTP objects from traffic
* Suspicious file **fakeurl.htm** identified

---

## 🚨 Key Findings

* One internal system exhibited unusually high communication with multiple hosts, which is not typical behavior
* Repeated DNS failures were observed, suggesting possible domain probing or automated requests
* Suspicious HTTP activity, including repeated requests, indicates potential malicious interaction
* Evidence of file transfers to external systems raises concern for possible data exfiltration

---

## 🧠 Threat Assessment

Based on the observed behavior, the system is likely compromised. The traffic patterns suggest:

* Possible Command & Control (C2) communication with external servers
* Suspicious outbound activity that may indicate data exfiltration
* Automated or scripted behavior within the network

---

## 🛡️ Recommendation

* Immediately isolate the affected system to prevent further communication
* Perform a detailed forensic and malware analysis
* Monitor outbound traffic for similar patterns across the network
* Strengthen endpoint security and apply stricter network controls

---

## 🛠️ Tools Used

* Wireshark for packet-level traffic analysis
* Network traffic inspection and protocol analysis (DNS, HTTP, TCP, SMB)

---

## 🚀 Skills Demonstrated

* Network Traffic Analysis and Packet Inspection
* Threat Detection and Behavioral Analysis
* Protocol Analysis (DNS, HTTP, Kerberos, SMB)
* Incident Investigation and Reporting

---

## 🚀 Why This Matters

This project reflects real-world investigation practices used in Security Operations Centers (SOC). It demonstrates the ability to analyze network traffic, identify abnormal behavior, and make informed decisions about potential security threats.

---

## 📌 Conclusion

The analysis identified a system exhibiting abnormal communication patterns and suspicious network activity. These indicators strongly suggest a potential compromise and possible data exfiltration. Immediate containment and further investigation are recommended to mitigate risk.


