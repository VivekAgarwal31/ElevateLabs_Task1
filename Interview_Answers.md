# 💬 Network Scanning – Interview Answers  
**By:** Vivek Agrawal  
**Date:** October 20, 2025  
**Topic:** Port Scanning & Network Security Fundamentals  

---

## 1️⃣ What is an open port?
An **open port** is a network port on a device or server that is actively accepting TCP or UDP connections.  
It indicates that a specific service or application is listening for incoming requests. For example, port **80** is usually open for **HTTP** web traffic.

---

## 2️⃣ How does Nmap perform a TCP SYN scan?
Nmap sends a **TCP SYN** packet to the target port (the first step in the TCP handshake).  
- If it receives a **SYN/ACK**, the port is **open**.  
- If it receives a **RST**, the port is **closed**.  
- If there’s no response or an ICMP unreachable message, the port is **filtered**.  
Nmap then sends a **RST** packet to avoid completing the full handshake, making it a “**stealth scan**.”

---

## 3️⃣ What risks are associated with open ports?
Open ports expose network services that could be exploited by attackers. Common risks include:  
- **Unauthorized access** through weak credentials.  
- **Exploitation of service vulnerabilities** (e.g., outdated software).  
- **Information disclosure** through banners or responses.  
- **Increased attack surface** for malware or intrusion attempts.

---

## 4️⃣ Explain the difference between TCP and UDP scanning.
- **TCP scanning:** Relies on the three-way handshake (SYN, SYN/ACK, ACK). Responses clearly indicate open or closed ports.  
- **UDP scanning:** Sends UDP packets and infers the state based on ICMP “port unreachable” replies or lack of response. It’s slower and less reliable because many systems drop UDP probes silently.

---

## 5️⃣ How can open ports be secured?
- **Close unnecessary ports** or disable unused services.  
- **Use firewalls** to restrict access to trusted IPs.  
- **Implement authentication and encryption** (e.g., SSH keys, HTTPS).  
- **Regularly patch and update** software.  
- **Monitor network traffic** to detect unusual port activity.

---

## 6️⃣ What is a firewall's role regarding ports?
A **firewall** controls network traffic based on configured security rules.  
It determines which ports and services are **allowed** or **blocked** for inbound and outbound connections, preventing unauthorized access to sensitive systems.

---

## 7️⃣ What is a port scan and why do attackers perform it?
A **port scan** is the process of probing a target to identify open or closed ports and active services.  
Attackers use it to:  
- **Map a network’s attack surface.**  
- **Identify exploitable services.**  
- **Find weak or outdated applications.**  
Ethical hackers perform port scans during security assessments to discover vulnerabilities before attackers do.

---

## 8️⃣ How does Wireshark complement port scanning?
**Wireshark** captures and analyzes live packet data during or after a scan.  
It helps visualize the SYN, SYN/ACK, and RST packets exchanged during Nmap scans, confirming port states.  
Analysts use it to verify scanning behavior, detect anomalies, and understand how services respond to probes.

---

> ✨ *Prepared by Vivek Agrawal — Elevate Labs CyberSecurity Internship (Interview Q&A) — October 2025.*
