# Task 8: Network Traffic Analysis with Wireshark

## Objective
Capture and analyze network traffic using Wireshark to identify protocols, analyze communication patterns, detect potential anomalies, and evaluate security practices.

---

## Steps Performed

### 1. Setup
- Installed Wireshark (`sudo apt-get install wireshark` on Ubuntu).
- Configured user permissions with:
  ```bash
  sudo usermod -a -G wireshark $USER
  
2. Packet Capture

Started capture on local network.
Generated HTTP and DNS traffic by browsing websites.
Stopped capture after a few minutes and saved results as wireshark_capture.pcap.


3. Applied Filters

HTTP traffic: http
Web traffic on port 80: tcp.port == 80
DNS queries: dns
Specific IP analysis: ip.addr == 192.168.1.1


4.Analysis Findings
Protocol Identification
Protocols observed: Ethernet, IP, TCP, DNS, HTTP.
Majority of traffic was TCP-based.

5.Traffic Flow Analysis

Outbound DNS queries observed (port 53) for resolving website names.
HTTP requests and responses visible, including unencrypted headers.

6.Security Observations
Unencrypted HTTP traffic: Detected (headers and payload readable).
DNS queries: Visible in plaintext (potential for data leakage).
HTTPS traffic: Not captured in detail due to encryption, only TLS handshakes visible.

7.Performance Metrics

Average round-trip time (RTT) for DNS queries ~ 25ms.
Some TCP retransmissions observed, suggesting mild packet loss.

8.Anomaly Detection
No suspicious traffic patterns identified in this sample capture.
Normal browsing behavior detected.
