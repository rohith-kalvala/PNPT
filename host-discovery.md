# Host Discovery (Active Systems on a Network)

Active scanning means you send packets to the network and analyze responses to find live hosts.

## 🎯 Goal

Identify:

- Live hosts (IPs that are up)
- Network range
- Possible targets for further testing

## 🛠️ Common Tools

### 1️⃣ Netdiscover

Uses ARP requests to find devices in local network.

**Basic usage:**
```bash
sudo netdiscover
```

**Scan specific range:**
```bash
sudo netdiscover -r 192.168.1.0/24
```

📌 **Output shows:**

- IP address
- MAC address
- Vendor (device type)

### 2️⃣ arp-scan

Another ARP-based scanner, often faster and more flexible.

**Install (if needed):**
```bash
sudo apt install arp-scan
```

**Scan local network:**
```bash
sudo arp-scan --localnet
```

**Scan range:**
```bash
sudo arp-scan 192.168.1.0/24
```

### 3️⃣ Nmap

Use tools like:

🔹 **Nmap**
```bash
nmap -sn 192.168.1.0/24
```

## 📋 Example: Netdiscover Scan

**Command:** `netdiscover -r 192.168.232.0/24` (r stands for range)

```
Currently scanning: Finished!   |   Screen View: Unique Hosts              
                                                                            
 47 Captured ARP Req/Rep packets, from 4 hosts.   Total size: 2820          
 _____________________________________________________________________________
   IP            At MAC Address     Count     Len  MAC Vendor / Hostname      
 -----------------------------------------------------------------------------
 192.168.232.1   00:50:56:c0:00:08     41    2460  VMware, Inc.             
 192.168.232.2   00:50:56:ec:cc:0a      3     180  VMware, Inc.             
 192.168.232.129 00:0c:29:5d:53:3f      1      60  VMware, Inc.             
 192.168.232.254 00:50:56:ee:11:fd      2     120  VMware, Inc.  
```

### Result of the Output:

**The VM machine which needs to be scanned:** `192.168.232.129`