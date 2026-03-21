# Nmap Cheat Sheet

Nmap (Network Mapper) is an open source tool for network exploration and security auditing. Here are some useful commands and options:

## Basic Commands

- `nmap <target>`: Basic scan of a target.
- `nmap -sP <target>`: Ping scan to determine live hosts.
- `nmap -sS <target>`: SYN scan (stealth scan).

## Service Version Detection

- `nmap -sV <target>`: Detect service versions.

## Operating System Detection

- `nmap -O <target>`: Detect operating system.

## Aggressive Scan

- `nmap -A <target>`: Aggressive scan, includes OS detection and service version detection.

## Output Options

- `nmap -oN <output_file>`: Normal output to a file.
- `nmap -oX <output_file>`: XML output to a file.
- `nmap -oG <output_file>`: Greppable output to a file.

## Scanning Multiple Targets

- `nmap <target1> <target2>`: Scan multiple targets.
- `nmap <target>/24`: Scan an entire subnet.

## Security Scans

- `nmap --script=<script>`: Use specific scripts for more detailed scanning.
- `nmap -sC <target>`: Run default scripts for scanning.

## ⚡ Quick Scan Types (Remember: **S T U A P**)

|Scan|Command|Meaning|
|---|---|---|
|SYN Scan|`nmap -sS <target>`|Stealth / most common|
|TCP Connect|`nmap -sT <target>`|Full TCP connection|
|UDP Scan|`nmap -sU <target>`|UDP ports|
|ACK Scan|`nmap -sA <target>`|Firewall check|
|Ping Scan|`nmap -sn <target>`|Only discover hosts|

🧠 **Memory trick:**  
**S T U A P → "Scan The UDP And Ping"**

## Tips

- Always ensure that you have permission to scan a network.
- Use `-v` for verbose output to see what's happening during a scan.

---

Current Date and Time (UTC): 2026-03-21 11:43:45
Current User's Login: rohith-kalvala