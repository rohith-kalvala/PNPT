# Configuring Wireshark

## Steps:

1. Launch the interception tool (e.g., Burp Suite) and create a temporary project, then click Next.

2. Open Firefox:
   - Click on the menu (three lines)
   - Go to Settings → General → Network Settings → Settings
   - Select Manual proxy configuration
   - Set:
     - HTTP Proxy: 127.0.0.1
     - Port: 8080
   - Click OK

3. Download the CA certificate from the proxy tool (e.g., Burp).

4. Import the certificate in Firefox:
   - Go to Settings → Privacy & Security → Certificates → View Certificates
   - Click Import
   - Select the downloaded certificate and trust it

5. Open the target website in the browser.

6. Enable interception in the proxy tool and forward the requests as needed.