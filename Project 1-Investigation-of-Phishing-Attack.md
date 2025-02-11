# 🚨 **Project: Phishing Attack Investigation** 🐟

## 📜 **Introduction**
Phishing attacks are one of the most prevalent **cybersecurity threats** today, where attackers deceive individuals into revealing **sensitive information** by pretending to be a trustworthy entity. This project aims to equip you with the necessary skills to **identify**, **investigate**, and **respond** to phishing attacks effectively. 🔍📧

## 🎓 **Pre-requisites**
Before you start, make sure you have:
- A **basic understanding of email systems** 📧
- Familiarity with **phishing techniques** 🐟
- Knowledge of **email analysis tools** 🛠️

## 🧰 **Lab Set-up and Tools**

To carry out a phishing attack investigation, you'll need a **simulated environment** and tools to analyze phishing emails. Here's the detailed setup:

### 1. **Email Server Simulation** 🖥️
**Description**: Set up a local **email server** or use an **email simulation service** to receive and send emails. This ensures a safe environment to analyze phishing emails without risking your real email account. 🔐

**Tools**: 
- **Halon MTA**: Flexible email server software 💻
- **MailCatcher**: A simple SMTP server that captures emails 📥
- **Mutt**: A text-based email client for UNIX systems 🐧

### 2. **Phishing Email Samples** 🐟
**Description**: Obtain phishing email samples to analyze. These can be sourced from **public repositories**, **cybersecurity forums**, or created for **educational purposes**.

**Tools**:
- **PhishTank**: A collaborative clearinghouse for phishing data 🌐
- **OpenPhish**: Continuously updated list of active phishing URLs 🛑

### 3. **Email Analysis Tools** 🔍
**Tools**:
- **Thunderbird**: Open-source email client by Mozilla 📧
- **PhishTool**: Specifically designed for phishing email analysis 🛠️
- **Email Header Analysis Tools**: Tools like **MXToolbox** or **EmailHeaders.net** for parsing and analyzing email headers 📑

## ⚙️ **Setting Up the Lab Environment**

### 1. **Install Thunderbird** 📥
- Download and install **Thunderbird** from the [official website](https://www.thunderbird.net/) 🖥️
- Set up an email account using either a **real** or **simulated** email server 📧

### 2. **Set Up Email Server Simulation** 🖥️

- Install **MailCatcher**:
  ```sh
  gem install mailcatcher
  mailcatcher
  ### 2. **Set Up Email Server Simulation** 🖥️

- **Access captured emails** through **MailCatcher**'s web interface:
  Open your browser and visit [http://127.0.0.1:1080/](http://127.0.0.1:1080/) to view captured emails 📬

- **Configure Thunderbird** to connect to the **MailCatcher** SMTP server:
  - **SMTP server**: `127.0.0.1`
  - **SMTP port**: `1025` (default MailCatcher SMTP port)
  - No **username** or **password** is needed for this local configuration.

- Once **MailCatcher** is running, send **test emails** through **Thunderbird** to check if they appear in the **MailCatcher** interface. The emails should be visible at [http://127.0.0.1:1080/](http://127.0.0.1:1080/). 📬

### 3. **Obtain Phishing Email Samples** 🐟
- Download phishing samples from **PhishTank** or **OpenPhish** 🌐
- Import the samples into **Thunderbird** for analysis 📥

### 4. **Install and Configure PhishTool** 🛠️
- Register for a free account at **PhishTool** 🌟
- Follow the setup instructions provided to integrate **PhishTool** with **Thunderbird** ⚙️

