# Windows Sysmon Splunk Detection Lab

## Description
This project demonstrates how to detect common attack patterns in a Windows environment using **Sysmon** and **Windows Event Logs**, with logs forwarded to **Splunk** for analysis.

The lab simulates real-world attacker behavior and shows how these activities are captured and queried in Splunk.

---

## Lab Setup
- Windows Server (Domain Controller)
- Windows 10 (Client Machine)
- Kali Linux (Splunk Enterprise Server)
- All systems on the same subnet
- Splunk Universal Forwarder installed on both Windows machines
- Sysmon installed on both Windows machines
- Logs forwarded to Splunk index: `winevents`

---

## Attacks Simulated

### 1. Brute Force Attack
- Multiple failed login attempts followed by a successful login
- Event Codes: 4625, 4624  
- Detection file: [Brute Force Detection](detections/brute-force.md)

---

### 2. Privilege Escalation
- User added/removed from privileged groups
- Event Codes: 4728, 4729 
- Detection file: [Privilege Escalation Detection](detections/privilege-escalation.md)

---

### 3. Lateral Movement
- Remote logon from one machine to another
- Event Code: 4624 (LogonType 3)  
- Detection file: [Lateral Movement Detection](detections/lateral-movement.md)

---

### 4. PowerShell Execution (Sysmon)
- PowerShell activity captured using Sysmon Operational logs
- Event Codes: 1, 4  
- Detection file: [PowerShell Sysmon Detection](detections/powershell-sysmon.md)

---

## Key Learning Points
- How to forward Windows logs to Splunk using Universal Forwarder  
- How Sysmon enhances visibility into process and script execution  
- How to detect common attack techniques using Splunk queries  
- Understanding why some logs may not appear initially and how to troubleshoot them  

---

│ └── powershell-sysmon.md
└── /screenshots
├── brute-force.png
├── privilege-escalation.png
├── lateral-movement.png
└── powershell-sysmon.png
