# Nmap Cheat Sheet

Nmap (Network Mapper) is an open source tool for network exploration and security auditing. Here are some useful commands and options:

## Basic Commands

- `nmap <target>`: Basic scan of a target.
- `nmap -sP <target>`: Ping scan to determine live hosts.
- `nmap -sS <target>`: SYN scan (stealth scan).

## Scan Types

| Scan Type       | Command             | Purpose                                    |
| --------------- | ------------------- | ------------------------------------------ |
| **SYN Scan**    | `nmap -sS <target>` | 🔥 Stealth scan (half-open, most used)     |
| **TCP Connect** | `nmap -sT <target>` | Full TCP connection (noisy)                |
| **UDP Scan**    | `nmap -sU <target>` | Scan UDP ports (slow)                      |
| **ACK Scan**    | `nmap -sA <target>` | Check firewall rules (filtered/unfiltered) |
| **Ping Scan**   | `nmap -sn <target>` | Discover live hosts only                   |

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

## Tips

- Always ensure that you have permission to scan a network.
- Use `-v` for verbose output to see what's happening during a scan.

---
