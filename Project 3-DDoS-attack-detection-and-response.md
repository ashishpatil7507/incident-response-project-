 # ⚡ Project 3: DDoS Attack Detection and Response 🚨 

  

## 🔍 Introduction
A **Distributed Denial of Service (DDoS) attack** aims to overwhelm a network, service, or server with excessive traffic from multiple sources, making it **unavailable** to legitimate users. Detecting and responding to DDoS attacks is crucial for ensuring the **availability, security, and performance** of online services. 

In this project, you will **learn how to detect and mitigate DDoS attacks** using industry-standard tools and techniques.

## ✅ Pre-requisites
Before starting, ensure you have the following:
- 🌐 **Basic understanding of networking concepts** (IP addressing, routing, etc.)
- ⌨️ **Familiarity with Linux command line**
- 🛡️ **Knowledge of common network protocols** (HTTP, TCP/IP, UDP, etc.)
- 💻 **System Requirements**: 
  - A computer with **8GB RAM** and **20GB free disk space**
  - **Virtualization software** (VirtualBox, VMware, etc.)

## ⚙️ Lab Set-up and Tools
### 🛠️ Lab Set-up
1. **Virtual Machines (VMs):**
   - **VM1 (Attacker)**: Kali Linux (used to launch DDoS attacks)
   - **VM2 (Victim)**: Ubuntu Server (simulates a target system)
   - **VM3 (Monitoring & Response)**: Ubuntu Desktop with DDoS detection tools

2. **Network Configuration:**
   - Create a **virtual network** where all VMs are connected.
   - Assign **static IPs** for easier identification.

### ⚙️ Tools Used
- 🔦 **Wireshark**: Network protocol analyzer
- 🔦 **tcpdump**: Command-line packet analyzer
- 🔦 **DDoSify**: DDoS attack simulation tool
- 🔦 **Snort**: Network Intrusion Detection System (IDS)
- 🔦 **fail2ban**: Bans IPs showing malicious activity
- 🔦 **netstat**: Analyzes network connections

## 🔧 Tasks

### 💥 Task 1: Simulate a DDoS Attack
**Step 1**: Install DDoSify on the Attacker Machine.
```bash
sudo apt-get update
sudo apt-get install ddosify
```
**Step 2**: Launch a simulated DDoS attack against the Victim Machine.
```bash
ddosify -t http://<Victim-IP> -n 1000 -c 100
```
**👩‍💻 Expected Outcome**: The Victim Machine's web server should become **unresponsive** due to high traffic.

---
### 🕵️ Task 2: Capture Network Traffic
**Step 1**: Install Wireshark and tcpdump on the Monitoring Machine.
```bash
sudo apt-get update
sudo apt-get install wireshark tcpdump
```
**Step 2**: Capture traffic using tcpdump.
```bash
sudo tcpdump -i eth0 -w ddos-attack.pcap
```
**👩‍💻 Expected Outcome**: A **.pcap file** (ddos-attack.pcap) containing captured network traffic.

---
### 📊 Task 3: Analyze Traffic with Wireshark
**Step 1**: Open the captured pcap file in Wireshark.
```bash
wireshark ddos-attack.pcap
```
**Step 2**: Identify **high-traffic IP addresses**.
**👩‍💻 Expected Outcome**: A list of **suspicious IPs generating excessive traffic**.

---
### 🔍 Task 4: Detect DDoS Attack with Snort
**Step 1**: Install Snort on the Monitoring Machine.
```bash
sudo apt-get update
sudo apt-get install snort
```
**Step 2**: Configure Snort to detect DDoS attacks.
Edit the Snort configuration file `/etc/snort/snort.conf` to include detection rules.

**Step 3**: Run Snort in IDS mode.
```bash
sudo snort -A console -q -c /etc/snort/snort.conf -i eth0
```
**👩‍💻 Expected Outcome**: Snort detects and **alerts** for potential DDoS attack patterns.

---
### 🛑 Task 5: Mitigate DDoS Attack with fail2ban
**Step 1**: Install fail2ban on the Victim Machine.
```bash
sudo apt-get update
sudo apt-get install fail2ban
```
**Step 2**: Configure fail2ban to detect and ban malicious IPs.
Edit the configuration file `/etc/fail2ban/jail.local`.
```ini
[http-get-dos]
enabled = true
port = http,https
filter = http-get-dos
logpath = /var/log/apache2/access.log
maxretry = 300
findtime = 300
bantime = 3600
```
**Step 3**: Restart fail2ban.
```bash
sudo systemctl restart fail2ban
```
**👩‍💻 Expected Outcome**: Malicious **IP addresses get banned**, reducing attack impact.

---
## 📚 Additional Resources
- [Wireshark Documentation](https://www.wireshark.org/docs/)
- [Snort User Manual](https://www.snort.org/documents)
- [fail2ban Documentation](https://www.fail2ban.org/wiki/index.php/Main_Page)
- [DDoSify GitHub Repository](https://github.com/ddosify/ddosify)

---
### 🎉 Congratulations! 
You've successfully completed the **DDoS Attack Detection and Response** project. This hands-on experience enhances your skills in **cybersecurity, intrusion detection, and incident response**, making you proficient in tackling real-world cyber threats! ✨
```

