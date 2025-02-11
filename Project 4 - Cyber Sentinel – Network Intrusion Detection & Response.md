
# 🔥 Project 4: Cyber Sentinel – Network Intrusion Detection & Response 🛡️

## 🔍 Introduction
Network **intrusion detection** is a crucial part of **cybersecurity**. It involves monitoring and analyzing network traffic for **unauthorized access** or **malicious activities**. This project will help you set up an **Intrusion Detection System (IDS)**, detect network intrusions, and respond effectively.

## ✅ Pre-requisites
Before starting, ensure you have the following:
- 🌐 **Basic networking knowledge** (IP addresses, subnets, ports, etc.)
- 🛡️ **Understanding of network security concepts**
- ⌨️ **Basic knowledge of Linux command line**

## ⚙️ Lab Set-up and Tools
### 🖥️ Network Architecture
- **Host Machine**: The main computer managing the virtual environment.
- **Virtual Machines (VMs)**:
  - 🛡️ **IDS VM**: Runs Snort for intrusion detection.
  - 💻 **Client VM**: Represents a user in the network.
  - 🎭 **Attacker VM**: Simulates a hacker attempting an intrusion.

### 🛠️ Tools Used
- **VirtualBox**: Open-source virtualization software.
- **Ubuntu**: Linux distribution for VMs.
- **Snort**: Open-source **Intrusion Detection System (IDS)**.
- **Wireshark**: Network protocol analyzer for traffic inspection.
- **Metasploit**: Penetration testing framework for simulating attacks.

## 🛠️ Lab Environment Setup

### 🔧 Step 1: Install VirtualBox
Download and install VirtualBox from the [official website](https://www.virtualbox.org/).

### 🔧 Step 2: Create Virtual Machines
#### IDS VM (Ubuntu)
```bash
sudo apt-get update
sudo apt-get install snort
```
- Configure Snort to monitor network traffic.

#### Client VM (Ubuntu)
- Ensure it is connected to the **same network** as the IDS VM.

#### Attacker VM (Kali Linux)
- Comes **pre-installed** with Metasploit and other **penetration testing** tools.

### 🔧 Step 3: Configure Network Settings
- Set all VMs to use a **Host-Only Adapter** in VirtualBox.

### 🔧 Step 4: Install Additional Tools
#### Wireshark (For Traffic Analysis)
```bash
sudo apt-get install wireshark
```

## 🚀 Tasks

### 🕵️ Task 1: Setting Up and Configuring Snort
**Objective**: Set up Snort to **monitor** network traffic and detect intrusions.

#### Steps:
1. Install Snort on the IDS VM (if not already installed).
2. Configure Snort:
   ```bash
   sudo nano /etc/snort/snort.conf
   ```
   - Set the **HOME_NET** variable to your **virtual network IP range**.
   - Add **intrusion detection rules**.
3. Start Snort in IDS mode:
   ```bash
   sudo snort -A console -q -c /etc/snort/snort.conf -i eth0
   ```
**👩‍💻 Expected Outcome**: Snort logs **alerts** for suspicious network activities.

---

### 💥 Task 2: Generating Network Traffic
**Objective**: Generate **normal** and **malicious** traffic to test IDS functionality.

#### Steps:
1. On **Client VM**, generate normal traffic using:
   ```bash
   ping <IDS_VM_IP>
   curl http://<IDS_VM_IP>
   ```
2. On **Attacker VM**, simulate an attack using Metasploit:
   ```bash
   msfconsole
   use auxiliary/scanner/portscan/tcp
   set RHOSTS <Client_VM_IP>
   run
   ```

**👩‍💻 Expected Outcome**:
- Normal traffic passes without triggering alerts.
- Malicious traffic **triggers alerts** in Snort logs.

---

### 📊 Task 3: Analyzing Network Traffic with Wireshark
**Objective**: Capture and analyze network packets to identify threats.

#### Steps:
1. Start Wireshark on the IDS VM and **select the monitoring interface**.
2. Capture traffic while performing Task 2.
3. Use filters to identify attack patterns:
   ```
   tcp.flags.syn == 1 && tcp.flags.ack == 0  # SYN Scans
   ip.addr == <Attacker_IP>  # Filter Attacker Traffic
   ```

**👩‍💻 Expected Outcome**:
- **Detailed packet analysis** with traffic patterns.
- Identified **attack sources** and methods.

---

### 🛑 Task 4: Responding to Detected Intrusions
**Objective**: Implement response actions to detected attacks.

#### Steps:
1. Review Snort logs for suspicious activity.
2. Block the attacker's IP using **iptables**:
   ```bash
   sudo iptables -A INPUT -s <Attacker_IP> -j DROP
   ```
3. Modify **firewall rules** to prevent similar attacks.

**👩‍💻 Expected Outcome**:
- Attacker **blocked** from further access.
- Improved **network security** measures.

---

## 📚 Additional Resources
- [Snort Documentation](https://www.snort.org/documents)
- [Wireshark User Guide](https://www.wireshark.org/docs/)
- [Metasploit Documentation](https://docs.metasploit.com/)
- [VirtualBox User Manual](https://www.virtualbox.org/manual/)

---

### 🎉 Congratulations!
You've successfully completed the **Network Intrusion Detection and Response** project. You now have hands-on experience in **intrusion detection, packet analysis, and attack mitigation**, essential for any **cybersecurity professional**! 🚀
```

