# Project 3: Network Intrusion Detection and Response 🚨

## Introduction 🌐
Network intrusion detection is a crucial aspect of cybersecurity. It involves monitoring and analyzing network traffic for signs of unauthorized access or malicious activity. This project aims to equip you with the skills to set up an **Intrusion Detection System (IDS)**, detect network intrusions, and respond effectively. 

## Pre-requisites 🎓
- **Basic networking knowledge** (IP addresses, subnets, ports, etc.)
- Familiarity with **network security concepts** 🔐
- Basic knowledge of **Linux command line** 🖥️

## Lab Set-up and Tools 🛠️

### Network Diagram 📊
![Network Diagram](https://example.com/network_diagram.png)

### Lab Environment Components 🖥️
1. **Host Machine**: The primary machine used for setting up and managing the virtual environment.
2. **Virtual Machines (VMs)**: Simulated machines used to create the network environment.
   - **IDS VM**: A virtual machine running the **Intrusion Detection System (IDS)**.
   - **Client VM**: A virtual machine representing a client within the network.
   - **Attacker VM**: A virtual machine simulating an external attacker.

### Tools 🧰
- **VirtualBox**: Open-source virtualization software by Oracle.
- **Ubuntu**: Linux distribution used for the VMs.
- **Snort**: An open-source **network intrusion detection system (NIDS)**.
- **Wireshark**: A network protocol analyzer used for capturing and analyzing network traffic.
- **Metasploit**: A penetration testing framework used to simulate attacks.

## Setting Up the Lab Environment ⚙️

#### 1. Install VirtualBox
- Download and install **VirtualBox** from the [official website](https://www.virtualbox.org/) 🖥️

#### 2. Create Virtual Machines (VMs) 💻
- **IDS VM**: 
  - Create a new VM and install **Ubuntu**.
  - Install **Snort**:
    ```sh
    sudo apt-get update
    sudo apt-get install snort
    ```
  - Configure **Snort** for basic intrusion detection.

- **Client VM**:
  - Create a new VM and install **Ubuntu**.
  - Ensure it is connected to the same network as the **IDS VM**.

- **Attacker VM**:
  - Create a new VM and install **Kali Linux**.
  - **Kali Linux** comes pre-installed with **Metasploit** and other penetration testing tools.

#### 3. Configure Network Settings 🌐
- Set all VMs to use a **Host-Only Adapter** in VirtualBox to ensure they are on the same virtual network and isolated from the host machine’s network.

#### 4. Install and Configure Tools 🛠️
- **Wireshark**: Install **Wireshark** on the IDS VM for traffic analysis.
  ```sh
  sudo apt-get install wireshark
