# Email Address Discovery Techniques

## Overview
Email addresses are critical in pentesting because they act as identifiers for users, access points for systems, and a foundation for reconnaissance and authentication testing.

## Why Email Addresses Matter in Pentesting

### 1. Emails = Usernames (Entry Point)
In most organizations: **Email = login ID**
- Email addresses serve as the primary identifier for user accounts
- Often used as usernames in internal systems and applications
- Essential for gaining initial access points

### 2. Helps Test Authentication Systems
With valid emails, testers can check:
- Login portals (VPN, O365, internal apps)
- Password policies
- Account lockout mechanisms
- MFA enforcement
- Authentication bypass vulnerabilities

### 3. Enables OSINT & Reconnaissance
Emails help gather more intelligence through:
- LinkedIn profiles
- GitHub accounts
- Data breaches (HaveIBeenPwned, etc.)
- Public documents with metadata
- Social media profiles

### 4. Phishing Simulation (Social Engineering)
In authorized pentests, emails are used to:
- Simulate phishing campaigns
- Test user awareness
- Measure click rates / credential submission
- Assess human vulnerabilities

### 5. Identifying Internal Structure
Email formats reveal patterns such as:
- `firstname.lastname@company.com`
- `empID@company.com`

From this, testers can:
- Predict other email addresses
- Map organizational hierarchy
- Identify departments (e.g., hr@, finance@)
- Understand naming conventions

### 6. Helps in Lateral Movement Testing
Once inside a system:
- Emails help identify other users
- Used for internal enumeration
- Helps simulate how an attacker would move across systems
- Enables privilege escalation vectors

## Tools & Resources for Email Discovery

### Popular Email Discovery Tools

1. **Hunter.io** - Email finder and verification service
   - Search for emails by domain
   - Verify email validity
   - Domain search capabilities

2. **Phonebook.cz** - Comprehensive email search engine
   - Large database of public emails
   - Advanced search filters

3. **Voilanorbert.com** - Email discovery and verification
   - Find emails associated with individuals
   - Verify email addresses

4. **Clearbit Connect** - Email finding Chrome extension
   - Automatic email detection
   - Works with LinkedIn and other platforms
   - Shows company information

5. **VerifyEmailAddress.io** - Email verification service
   - Check email validity
   - Verify deliverability
   - Batch verification capabilities

## Email Discovery Methodology

1. **Passive Reconnaissance**
   - Search public records and databases
   - Use OSINT tools
   - Analyze company websites and documentation

2. **Pattern Recognition**
   - Identify naming conventions
   - Create email format patterns
   - Generate potential email addresses

3. **Verification**
   - Validate discovered emails
   - Check for active accounts
   - Use verification tools

4. **Documentation**
   - Record all found emails
   - Note sources and timestamps
   - Organize by department/role

## Best Practices

- **Always get proper authorization** before conducting email discovery
- Document all findings for the engagement report
- Respect privacy regulations (GDPR, etc.)
- Use multiple tools for cross-verification
- Combine automated tools with manual OSINT techniques
- Keep discovered emails secure and confidential

## References & Further Reading

- OWASP Testing Guide - Information Gathering
- Metasploit Email Enumeration Modules
- Nmap and associated scripts for email discovery
