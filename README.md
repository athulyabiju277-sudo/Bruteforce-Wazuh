#  Brute Force Attack Simulation & Detection using Wazuh SIEM

SOC Project | SIEM Detection | Log Analysis

##  Overview

This project demonstrates an end-to-end Security Operations Center (SOC) use case by simulating an SSH brute force attack and detecting it using Wazuh SIEM. It highlights both offensive (attack simulation) and defensive (log analysis and alerting) cybersecurity techniques.

---

##  Objectives

* Simulate brute force attack on SSH service
* Monitor and analyze authentication logs
* Detect malicious activity using SIEM
* Investigate alerts and identify attacker behavior

---

##  Tools & Technologies

* Wazuh SIEM (Log monitoring & threat detection)
* Kali Linux (Attacker machine)
* Ubuntu (Target + Wazuh server)
* Hydra (Brute force attack tool)
* SSH (Target service)

---

##  Architecture

Attacker (Kali Linux) → SSH Attack → Target (Ubuntu) → Log Generation → Wazuh Agent/Manager → Alert Detection → Dashboard Visualization

---

##  Methodology

### 1️ Environment Setup

* Installed Wazuh on Ubuntu system
* Configured dashboard and log monitoring
* Enabled SSH service on target system

---

### 2️ Attack Simulation

Performed brute force attack using Hydra:

```
hydra -l root -P /usr/share/wordlists/rockyou.txt ssh://<target-ip>
```

* Generated multiple failed login attempts
* Simulated real-world attack behavior

---

### 3️ Log Analysis

Authentication logs monitored from:

```
/var/log/auth.log
```

Sample log:

```
Failed password for root from <attacker-ip> port 22 ssh2
```

---

### 4️ Detection using Wazuh

Wazuh detected:

* Repeated failed login attempts
* Suspicious authentication patterns
* Brute force attack behavior

Alerts generated with:

* Rule IDs (e.g., 5710, 5712)
* Source IP identification
* Log correlation

---

##  Screenshots

###  Wazuh Dashboard

![Dashboard](wazuh-dashboard.png.jpeg)

###  Brute Force Attack (Hydra)

![Attack](hydra-attack.png.jpeg)

###  Log Evidence (auth.log)

![Logs](auth-log.png.jpeg)

###  Security Alerts

![Alerts](screenshots/alerts.png)

###  Alert Details

![Details](screenshots/alert-details.png)

---

##  Results

* Successfully simulated SSH brute force attack
* Generated multiple authentication failure logs
* Wazuh detected and alerted suspicious activity
* Attacker IP successfully identified

---

##  Key Learnings

* Understanding of brute force attack techniques
* Hands-on experience with SIEM (Wazuh)
* Log analysis and threat detection
* SOC workflow: Monitoring → Detection → Investigation

---

##  Conclusion

This project demonstrates the effectiveness of Wazuh SIEM in detecting brute force attacks through real-time log monitoring and rule-based analysis. It reflects practical SOC-level skills in threat detection and incident analysis.

---
