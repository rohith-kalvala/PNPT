# Gaining Root Access

## 1. Searchsploit

Searchsploit is a command-line search tool for Exploit-DB, which allows you to search for exploits and vulnerabilities in your system or targets. It can be used as follows:

```bash
searchsploit -w <search term>
```

This command will return a list of relevant exploits.

### Examples:
- Search for a specific software vulnerability:
  ```bash
  searchsploit <software>
  ```

- To view detailed information about an exploit:
  ```bash
  searchsploit -p <exploit_id>
  ```

---

## 2. Metasploit

Metasploit is an advanced framework for developing and executing exploit code against a remote target machine. You can install it on your system and use it to perform penetration testing. Below is a basic workflow:

1. **Start Metasploit Console**:
   ```bash
   msfconsole
   ```

2. **Search for an exploit**:
   ```bash
   search <exploit_name>
   ```

3. **Use the selected exploit**:
   ```bash
   use <exploit_path>
   ```
   After that, set the required options and run the exploit using `exploit` command.

### Key Commands:
- **set**: To set options like targets or payloads.
- **run**: To execute the exploit.

---

**Note**: Always ensure you have permission to test systems that you are attempting to exploit.