# 🌐 Network Scanning & Analysis Report  
**By:** Vivek Agrawal  
**Date:** October 20, 2025  
**Tool Used:** Nmap (v7.94)  
**Environment:** Kali Linux VM  

---

## 🧠 Overview
This task focused on identifying active hosts and open ports within the local subnet `192.168.2.0/24` using **TCP SYN scanning (`-sS`)**.  
The goal was to detect running services and assess potential security risks.

---

## ⚙️ Command Used
```bash
sudo nmap -sS 192.168.2.0/24 -T4 -oN nmap_task.txt
```

---

## 🖥️ Key Findings

| IP Address | Open Port(s) | Service | Risk | Remediation |
|-------------|--------------|----------|:----:|-------------|
| **192.168.2.1** | 3306/tcp | mysql | 🔴 High | Restrict MySQL to localhost/trusted hosts, enforce strong passwords, patch, and use firewall rules. |
| **192.168.2.2** | 53/tcp | domain (DNS) | 🟠 Medium | Restrict DNS to internal clients, disable unauthorized zone transfers, patch DNS software. |
| **192.168.2.254** | — | no open TCP ports (filtered) | 🟢 Low | Monitor and verify firewall rules; run targeted scans if access needed. |
| **192.168.2.128** | — | no open TCP ports (closed/reset) | 🟢 Low | Monitor; consider UDP or targeted scans if required. |

---

## 📊 Summary
- **Total Hosts Scanned:** 256  
- **Active Hosts:** 4  
- **Notable Services:** MySQL (`192.168.2.1`), DNS (`192.168.2.2`)  
- **Scan Duration:** 8.27 seconds  
- **Scan Type:** Stealth SYN Scan  

---

## 🔍 Risk Overview
- **High Risk:** Database service (MySQL) potentially exposed to the network.  
- **Medium Risk:** DNS service could leak internal information or allow unauthorized queries.  
- **Low Risk:** Other hosts filtered or closed; minimal immediate exposure.

---

## 🧾 Conclusion
The Nmap scan successfully identified two critical services within the subnet.  
Mitigating these risks requires **restricting external access**, **patching services**, and **regular monitoring** for new exposures.

---

## 📁 Files & Deliverables
- `nmap_task.txt` — raw Nmap scan output  
- `open_ports.md` — extracted findings in Markdown  
- `wireshark_screenshots/` — contains SYN/SYN-ACK evidence  
- `scan_capture.pcapng` — packet capture of the scan  

---

> ✨ *Prepared by Vivek Agrawal as part of the Day 1 of Elevate Labs Internship Task — October 2025.*
