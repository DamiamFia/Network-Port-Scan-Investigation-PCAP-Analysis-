# Network-Port-Scan-Investigation-PCAP-Analysis-
PCAP ANALYSIS
---
PROJECT OVERVIEW
---

This project demonstrates a Security Operations Center (SOC) investigation into a suspected port scanning activity using a captured network traffic file (PCAP). The goal is to identify malicious behavior, analyze attacker patterns, and document findings using industry-relevant tools.

---
OBJECTVIES
---
- Detect suspicious network activity
- Identify signs of port scanning
- Analyze attacker IP behavior
- Extract key indicators of compromise (IOCs)
-Simulate real-world SOC analysis workflow

---
TOOLS USED
---
- Wireshark – Packet analysis
- VirusTotal – IP reputation check
- AbuseIPDB – Threat intelligence lookup

---
DATASET
---

- File Name: soc_portscan_investigation
- Type: Network packet capture
- Scenario: Simulated network with suspected reconnaissance activity

---
INVESTIGATION STEPS
---
1. **Open PCAP File**
  - Load the .pcap file into Wireshark
  - Observe general traffic patterns

---
2. **Identify Suspicious Traffic**

  - Apply filters to detect scanning behavior:
    
        tcp.flags.syn == 1 and tcp.flags.ack == 0
  - This filter shows SYN packets, commonly used in port scans

---
3. **Analyze Source IP**
  - Look for IPs sending repeated SYN requests to multiple ports
  - Example suspicious behavior:
   
        High number of connection attempts
   
        Sequential port targeting

   ---
 4. **Check Destination Ports**

 - Identify ports being scanned ( 22, 80, 443)
 - Determine if scanning is:

        Sequential
    
        Random
    
        Targeted

---
 5. **Follow TCP Streams**
    
- Right-click → Follow → TCP Stream
- Analyze communication patterns

---
6. **Extract Indicators of Compromise (IOCs)**

- Indicator Type	Value
- Source IP	:XXX.XXX.XXX.XXX
- Target Ports:(22, 80, 443)
- Protocol : TCP
- Behavior :SYN Scan

---
7. **Threat Intelligence Lookup**
   
- Check IP on:
  
      VirusTotaL
  
      AbuseIPDB
  
      Determine if IP is known malicious

---
FINDINGS
---
- Detected port scanning activity from a single source IP
- Pattern indicates reconnaissance phase of an attack
- No successful connections established
- Activity matches SYN scan technique
  ---
 MITRE ATT&CK Mapping
 ---
- Tactic: Reconnaissance
- Technique: Active Scanning (T1595)

---
RECOMMENDATION 
---
- Block malicious IP at firewall
- Enable IDS/IPS alerts for scanning activity
- Monitor unusual connection attempts
- Implement rate limiting
---  
Skills Demonstrated
---
- Network traffic analysis
- Threat detection
- IOC extraction
- Use of Wireshark filters
- SOC investigation workflow
    


