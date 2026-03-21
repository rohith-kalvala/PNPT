# Enumeration
Enumeration is the phase where you go deeper after scanning to extract detailed information about services, users, shares, versions, etc.

Here’s a clean, practical list of enumeration tools used in penetration testing 👇

## 🔍 Enumeration Tools Cheat Sheet

### - 🌐 1. Network & Service Enumeration

🔹 Nmap: Service detection & scripts
  
  -`nmap -sV -sC target`

🔹 Netcat : Banner grabbing

  -`nc target 80`

### - 🌍 2. Web Enumeration

🔹 Nikto : Finds web vulnerabilities

  -`nikto -h http://target`
  
🔹 Dirb: Directory brute forcing

  -`dirb http://target`
  
🔹 Gobuster
  -`gobuster dir -u http://target -w wordlist.txt`
  
🔹 WhatWeb

  -`Detect technologies (CMS, frameworks)`
  -`whatweb target`


### -🧑‍💻 3. SMB / Windows Enumeration

🔹 Enum4linux

  -`enum4linux -a target`

🔹 SMBclient

  -`smbclient -L //target`
  
### -📡 4. DNS Enumeration

🔹 dnsenum

  -`dnsenum target.com`

🔹 dnsrecon
  -`dnsrecon -d target.com`

  
### - 🔐 5. SNMP Enumeration

🔹 SNMPwalk
  -`snmpwalk -v2c -c public target`
  
### -📧 6. Email / User Enumeration

🔹 theHarvester
  -` theHarvester -d target.com -b google`

### -🧠 7. All-in-One / Advanced
🔹 Metasploit Framework

  -` Auxiliary modules for enumeration`

use auxiliary/scanner/...
--
**🧩 Simple Workflow**

1️⃣ Scan → nmap
2️⃣ Web → nikto, gobuster
3️⃣ SMB → enum4linux
4️⃣ DNS → dnsenum
5️⃣ SNMP → snmpwalk
