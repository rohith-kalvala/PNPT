 Staged vs Stageless (Full) Payloads

Tool commonly used: Metasploit Framework

---

## 🧠 Core Idea

|Type|Description|
|---|---|
|**Staged Payload**|Delivered in **multiple steps** (stage + payload)|
|**Stageless (Full) Payload**|Delivered **all at once** in a single file|

---

# 🔗 1. Staged Payload

## 📌 Concept

Payload is split into:

1. **Stage 1 (small loader)**
2. **Stage 2 (full payload)**

👉 Stage 1 connects back and downloads Stage 2

---

## ⚙️ Example

windows/meterpreter/reverse_tcp

👉 Notice `/` → indicates **staged**

---

## 🔄 How It Works

1. Exploit sends small shellcode  
2. Target connects back  
3. Full payload (Meterpreter) is sent

---

## ✅ Advantages

- Smaller initial payload (easier to inject)
- Faster exploitation
- Useful in limited space (buffer overflow)

---

## ❌ Disadvantages

- Needs stable connection ❌
- More detectable (network activity)
- Can fail if stage 2 is blocked

---

# 📦 2. Stageless (Full) Payload

## 📌 Concept

Entire payload is sent in **one go**

👉 No second stage required

---

## ⚙️ Example

windows/meterpreter_reverse_tcp

👉 Notice `_` → indicates **stageless**

---

## 🔄 How It Works

1. Full payload delivered at once  
2. No additional download needed  
3. Direct execution

---

## ✅ Advantages

- More reliable ✅
- No extra network traffic
- Harder to interrupt

---

## ❌ Disadvantages

- Larger payload size ❌
- Easier to detect (signature-based AV)
- Harder to inject in memory-limited exploits

---

# 🎯 Key Difference (IMPORTANT)

|Feature|Staged|Stageless|
|---|---|---|
|Delivery|Multi-step|Single-step|
|Size|Small initial|Large|
|Reliability|Lower|Higher|
|Stealth|Less|More stable|
|Network Dependency|High|Low|

---

# 🧠 Easy Memory Trick

- `/` → **Staged** → “Split” payload
- `_` → **Stageless** → “Whole” payload

---

# 🔥 Real Pentesting Usage

|Scenario|Use|
|---|---|
|Exploit with limited buffer|Staged|
|Stable access needed|Stageless ✅|
|AV evasion|Depends (case-by-case)|

---

# 🚀 Practical Examples

### Staged:

use exploit/windows/smb/ms08_067_netapi  
set payload windows/meterpreter/reverse_tcp

---

### Stageless:

set payload windows/meterpreter_reverse_tcp

---

# 🧠 Pentester Insight

- Start with **staged** → easier to deliver
- Switch to **stageless** → for stability

👉 Many real-world attackers prefer **stageless for persistence**
