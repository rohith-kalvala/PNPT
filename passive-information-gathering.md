# Passive Information Gathering

Passive information gathering (reconnaissance) is the process of collecting information about a target without directly interacting with the target systems.

## 1. WHOIS & Domain Info

**whois (CLI)**
- ICANN lookup
- DomainTools

👉 **Finds:**
- Domain owner
- Registration details
- Name servers

## 2. Search Engines (Google Dorking)

**Google advanced search**

**Examples:**
```
site:company.com filetype:pdf
site:company.com "password"
```

👉 **Finds:**
- Public documents
- Sensitive exposed data

## 3. Email Enumeration Tools

- Hunter.io
- theHarvester
- Phonebook.cz

👉 **Finds:**
- Employee email patterns
- Public email addresses

## 4. OSINT Tools

- Maltego
- Recon-ng
- SpiderFoot

👉 **Aggregates:**
- Domains
- Emails
- Social profiles
- Infrastructure

## 5. Subdomain Enumeration

- crt.sh
- Amass (passive mode)
- Sublist3r

👉 **Finds:**
- Hidden subdomains
- Attack surface

## 6. Breach Data Tools

- HaveIBeenPwned
- DeHashed

👉 **Finds:**
- Leaked credentials
- Exposed users

## 7. Social Media & Professional Platforms

- LinkedIn
- Twitter

👉 **Finds:**
- Employee roles
- Org structure
- Technologies used

## 8. Metadata Extraction

- FOCA
- ExifTool

👉 **Extracts:**
- Author names
- Internal paths
- Software used

## Technology Detection Tools

We scan using tools like:
- buildwith.com
- wappalyzer
- whatweb

### Tool Details:

**Wappalyzer:**
Provides you the versions of the information on what that website is running on and this can help us find information on vulnerabilities using those.

**Whatweb (tool in kali):**
```
whatweb http://tesla.com (check on the site using this tool)
```

## References

- https://builtwith.com/?https%3A%2F%2Fcertifications.tcm-sec.com%2Fpnpt%2F
- https://www.wappalyzer.com/
- https://www.kali.org/tools/whatweb/