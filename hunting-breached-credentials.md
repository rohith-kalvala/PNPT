# Hunting Breached Credentials

Looking for breached (leaked) credentials is a critical component of penetration testing because it mirrors how attackers actually compromise systems in the real world.

## Why Hunting Breached Credentials Matters

### 🎯 1. Real Attackers Reuse Leaked Credentials

**The Reality:**
- Users frequently reuse passwords across multiple platforms
- When a site gets breached, attackers obtain valid email and password combinations
- These same credentials are often used in corporate systems

**Practical Attack Flow:**
```
User signs up on a random website
        ↓
Site gets breached
        ↓
Credentials are leaked
        ↓
Attacker tries same email + password on corporate systems
        ↓
Direct access gained (Credential Stuffing Attack)
```

**Impact:** Attackers leverage this method because it has a high success rate and requires minimal effort.

---

### 🔐 2. Tests Exposure of Your Organization

Checking breached credentials reveals critical information about your organization's security posture:

| Assessment Area | What It Reveals |
|---|---|
| **Employee Exposure** | Which employees have credentials in breach databases |
| **Active Threats** | Whether exposed credentials still work internally |
| **Password Hygiene** | Weak password reuse patterns across the organization |
| **Real Risk vs. Theoretical Risk** | Tangible vulnerabilities rather than theoretical ones |

**Key Question:** How many of your employees appear in breach databases with active credentials?

---

### 🧠 3. Valid Username + Password = Direct Access

**Why This Attack Method is Dangerous:**

| Factor | Credential Reuse Attack | Brute Force Attack |
|---|---|---|
| **Effort Required** | Minimal | High |
| **Alerts Triggered** | Few/None | Many |
| **Detection Difficulty** | High (looks legitimate) | Low (obvious pattern) |
| **Success Rate** | High | Low |

**Critical Insight:** This is one of the most effective and stealthy attack methods in the attacker's toolkit because it bypasses typical security controls.

---

### 📉 4. Helps Validate Security Controls

Testing with breached credentials answers the fundamental question: **"If a real leaked password is used, are we protected?"**

Verify these critical controls:

- ✅ **MFA Enforcement** – Is multi-factor authentication required?
- ✅ **Password Reset Policies** – Are compromised passwords forced to reset?
- ✅ **Account Lockout Mechanisms** – Do multiple login attempts trigger lockouts?
- ✅ **Detection Systems (SIEM)** – Are alerts generated for breach credential usage?
- ✅ **Behavior Analytics** – Are unusual login patterns detected?

**Testing Outcome:** Identifies gaps in your defensive security posture.

---

### 🔎 5. Reduces Guesswork in Penetration Testing

**Traditional Approach (Inefficient):**
- Random password guessing
- High noise, low success
- Time-consuming

**Breach Credential Approach (Effective):**
- Test known compromised credentials
- Higher success rate
- Faster identification of vulnerable accounts
- More realistic attack simulation

**Benefit:** Provides faster, more accurate penetration test results aligned with real-world attack methods.

---

### 📧 6. Tied to Email Enumeration

This creates a direct pipeline from reconnaissance to exploitation:

```
Email Enumeration Phase
        ↓
Identify valid emails in your organization
        ↓
Check breach databases for those emails
        ↓
Attempt login with breached credentials
        ↓
Exploitation Phase Begins
```

**Workflow Integration:** Breached credential hunting is the natural next step after email discovery, creating a seamless progression from recon to exploitation.

---

## Methodology: Hunting Breached Credentials

### Step 1: Gather Target Emails
- Use techniques from email-discovery-techniques.md
- Compile list of valid organizational email addresses

### Step 2: Query Breach Databases
- Check haveibeenpwned.com (HaveIBeenPwned API)
- Query other breach databases (Dehashed, LeakCheck, etc.)
- Document exposed credentials for each email

### Step 3: Attempt Authentication
- **Within Scope & Authorization Only**
- Test breached credentials against internal systems
- Document successful logins
- Note security controls that prevented access

### Step 4: Validate Security Posture
- Identify which controls prevented compromise
- Highlight gaps in detection and response
- Document findings for remediation

---

## Important: Scope and Authorization

⚠️ **Critical Requirement:** Only test breached credentials within explicitly authorized scope. Unauthorized credential testing violates laws including:
- Computer Fraud and Abuse Act (CFAA) in the US
- Computer Misuse Act in the UK
- Equivalent regulations in other jurisdictions

Always ensure you have written authorization before attempting any credential-based access.

---

## Summary

Hunting breached credentials is essential because it:
1. ✅ Reflects real attacker methods
2. ✅ Identifies exposed employees
3. ✅ Tests actual security controls
4. ✅ Provides direct access (highest impact)
5. ✅ Creates efficient penetration test workflows
6. ✅ Validates organizational resilience against real threats