# 📈 Level 3 Gate Test

**90 questions · Chapters 23–33 (Domains 1–3) · 90 minutes · Target: 63 / 90 (70%) to move on to Level 4**

This is a **half-length practice exam** in real exam style: mostly scenarios, with keywords like **BEST**, **MOST likely** and **FIRST**. Do it in one sitting with a 90-minute timer. Then mark it, write every miss in your **mistake journal**, and re-read the chapter given in the key.

---

## Section A — Threat Vectors & Attack Surfaces (Ch 23)

**1.** Attackers breached a managed service provider and used its remote-management tool to deploy ransomware to the provider's customers. Which threat vector is this?
A. Removable device  B. Default credentials  C. Supply chain  D. Watering hole

**2.** A vulnerability scan finds Telnet and FTP listening on a public web server. Which attack surface issue is this?
A. Shadow IT  B. Unsupported system  C. Image-based vector  D. Open service ports

**3.** Thousands of IoT cameras were taken over using their factory username and password. Which vector was used?
A. Default credentials  B. Supply chain  C. Message-based  D. Bluetooth

**4.** A hospital imaging system runs an operating system that no longer receives security updates. What is the BEST immediate action?
A. Disable its antivirus  B. Isolate it on a restricted network segment  C. Connect it directly to the internet  D. Ignore it until it fails

**5.** Which control BEST prevents visitors from joining the corporate LAN by plugging into lobby wall ports?
A. 802.1X port authentication  B. WPA3  C. DNS filtering  D. Full-disk encryption

**6.** A user plugs in a USB cable found in the car park; it acts as a keyboard and types malicious commands. This vector is:
A. Voice call  B. Removable device  C. Vulnerable software  D. Typosquatting

**7.** Which term describes ALL the possible points where an attacker could try to enter a system?
A. Attack surface  B. Threat vector  C. Exploit  D. Payload

**8.** Software installed on each endpoint, which must be patched on every device, is described as:
A. Agentless  B. Serverless  C. Client-based  D. Air-gapped

---

## Section B — Vulnerability Types (Ch 24)

**9.** A login form receives the input `' OR 1=1 --`. Which vulnerability is being targeted?
A. XSS  B. CSRF  C. Buffer overflow  D. SQL injection

**10.** What is the BEST way to prevent SQL injection?
A. Antivirus  B. Disk encryption  C. Longer passwords  D. Parameterized queries

**11.** A forum post contains a script that runs in the browser of every user who views the page. This is:
A. Reflected XSS  B. Directory traversal  C. SQL injection  D. Stored XSS

**12.** A program checks that a user may access a file, but an attacker swaps the file before the program opens it. This is a:
A. Memory leak  B. Race condition (TOC/TOU)  C. Collision  D. Downgrade

**13.** Malware inside a virtual machine gains access to the hypervisor and other VMs. This is:
A. Resource reuse  B. VM escape  C. Jailbreaking  D. Side-loading

**14.** A program writes more data than its allocated memory, overwriting the return address. Which OS protection randomizes memory locations to make this harder?
A. DLP  B. HSTS  C. ASLR  D. SAML

**15.** Attackers are exploiting a flaw for which the vendor has not yet released a fix. This is a:
A. Legacy vulnerability  B. Zero-day  C. Misconfiguration  D. Known vulnerability

**16.** Customer data leaked because a cloud storage bucket was set to public. Which vulnerability category BEST fits?
A. Race condition  B. Firmware  C. Misconfiguration  D. Zero-day

**17.** A widely used open-source logging library inside thousands of products contained a critical flaw. This BEST illustrates a:
A. Physical vulnerability  B. Supply chain (software provider) vulnerability  C. Mobile vulnerability  D. Cryptographic vulnerability

---

## Section C — Network Attacks (Ch 25)

**18.** An attacker sends small DNS queries to open resolvers with the victim's IP as the source address, producing huge responses to the victim. This is BEST described as:
A. DNS tunneling  B. Reflected and amplified DDoS  C. ARP poisoning  D. Evil twin

**19.** Users typing the correct bank URL are sent to a fraudulent site. Which control BEST prevents this?
A. DNSSEC  B. WPA3  C. RAID 5  D. Tokenization

**20.** An ARP table shows the default gateway's IP mapped to a workstation's MAC address. What is MOST likely occurring?
A. DNS hijacking  B. On-path attack via ARP poisoning  C. Jamming  D. Password spraying

**21.** An attacker captures a valid session token and reuses it to access the victim's account. This is:
A. Bluejacking  B. Brute force  C. Directory traversal  D. Credential replay

**22.** Two access points broadcast the company SSID; one belongs to an attacker in the car park. This is:
A. A rogue access point  B. Jamming  C. An evil twin  D. A honeynet

**23.** An employee connects a personal wireless router to an office network jack. This is a(n):
A. Evil twin  B. Honeypot  C. Deauthentication attack  D. Rogue access point

**24.** A browser connects to a bank over HTTP instead of HTTPS because an on-path attacker stripped TLS. Which control prevents this?
A. NAC  B. SNMPv3  C. DLP  D. HSTS

**25.** Large volumes of DNS queries with long, random-looking subdomains go to a single unknown domain. This MOST likely indicates:
A. A failing hard drive  B. Normal web browsing  C. DNS tunneling (data exfiltration)  D. RFID cloning

---

## Section D — Application, Password & Crypto Attacks; Indicators (Ch 26)

**26.** A web log shows `GET /view?file=../../../etc/passwd`. Which attack is this?
A. SSRF  B. CSRF  C. Directory traversal  D. XSS

**27.** One failed login occurred on each of 400 accounts from the same IP within ten minutes. This is MOST likely:
A. Brute force  B. Credential replay  C. Rainbow table  D. Password spraying

**28.** Which BEST protects stored password hashes against rainbow table attacks?
A. Encoding  B. Salting  C. Compression  D. Masking

**29.** An attacker forces a client and server to negotiate SSL 3.0 instead of TLS 1.3. This is a:
A. Collision attack  B. Replay attack  C. Birthday attack  D. Downgrade attack

**30.** A malicious site causes a logged-in user's browser to submit a money-transfer request to their bank. This is:
A. SSRF  B. CSRF  C. SQL injection  D. Privilege escalation

**31.** A user account logs in from London and, 20 minutes later, from Tokyo. Which indicator is this?
A. Impossible travel  B. Blocked content  C. Resource consumption  D. Out-of-cycle logging

**32.** The Windows Security log shows Event ID 1102 (audit log cleared) on a server. Which indicator does this represent?
A. Missing logs  B. Published/documented  C. Account lockout  D. Concurrent session usage

**33.** A standard user exploits a kernel flaw to run commands as SYSTEM. This is:
A. Horizontal privilege escalation  B. Session hijacking  C. Vertical privilege escalation  D. Downgrade

**34.** An attacker copies an employee's access badge using a hidden reader in a crowded lift. This is:
A. Tailgating  B. Bluesnarfing  C. Shoulder surfing  D. RFID cloning

---

## Section E — Mitigation & Hardening (Ch 27)

**35.** Which mitigation BEST prevents malware on an infected IoT device from reaching finance servers?
A. Segmentation  B. Screen locks  C. Masking  D. Job rotation

**36.** Kiosk computers must run only one approved application. Which control is BEST?
A. Application allow list  B. Block list  C. Antivirus only  D. Load balancer

**37.** A laptop shows signs of active malware. The security team wants it cut off from all network communication immediately. Which technique is this?
A. Isolation  B. Segmentation  C. Decommissioning  D. Tokenization

**38.** Which of the following is a hardening technique listed in SY0-701?
A. Enabling Telnet for remote admin  B. Removing unnecessary software  C. Sharing admin passwords  D. Disabling the host firewall

**39.** Systems keep drifting away from the approved secure configuration. Which mitigation BEST addresses this?
A. Honeypots  B. Decommissioning  C. Configuration enforcement  D. Steganography

**40.** A server is being retired. Which step is part of proper decommissioning?
A. Leaving it powered on in case it's needed  B. Removing it only from the asset inventory  C. Moving it to the screened subnet  D. Sanitizing its storage and revoking its accounts and certificates

**41.** Which mitigation limits the damage if a user's account is compromised?
A. Using a hub  B. Broadcasting the SSID  C. Least privilege  D. Public cloud buckets

**42.** A legacy controller can't be patched. Which mitigation is the BEST compensating control?
A. Giving all users admin rights  B. Isolation/segmentation with monitoring  C. Disabling logging  D. Removing the firewall

---

## Section F — PKI & Applied Cryptography (Ch 28)

**43.** Which component stores full-disk encryption keys and supports measured boot on a laptop?
A. HSM  B. CASB  C. TPM  D. Load balancer

**44.** A bank needs tamper-resistant, high-performance hardware to protect thousands of signing keys. Which is BEST?
A. HSM  B. TPM  C. USB drive  D. Secure Boot

**45.** Which allows a client to check the revocation status of a single certificate in real time?
A. CRL  B. OCSP  C. CSR  D. SAN

**46.** A certificate issued for `*.example.com` is a:
A. Wildcard certificate  B. Self-signed certificate  C. Code-signing certificate  D. Root certificate

**47.** What does a certificate signing request (CSR) contain?
A. The private key  B. The CRL  C. The CA's private key  D. The public key and identity information

**48.** An internal site shows a browser warning because its certificate was signed by its own private key. This certificate is:
A. Third-party  B. Extended validation  C. Wildcard  D. Self-signed

**49.** Which technique replaces card numbers with random values whose real values are stored in a secure vault?
A. Tokenization  B. Hashing  C. Steganography  D. Key stretching

**50.** Which technique makes brute-forcing stolen password hashes much slower?
A. Data masking  B. Base64 encoding  C. Key stretching (e.g., bcrypt, PBKDF2)  D. Compression

**51.** Hiding a secret message inside the pixels of an image is called:
A. Tokenization  B. Steganography  C. Salting  D. Hashing

**52.** Why are root CAs typically kept offline?
A. To save electricity  B. To protect the private key at the top of the chain of trust  C. Because browsers can't reach them  D. To speed up OCSP

---

## Section G — Architecture Models (Ch 29)

**53.** In a PaaS model, who is responsible for patching the operating system?
A. The cloud provider  B. The customer  C. The end user  D. Nobody

**54.** In every cloud service model, which remains the customer's responsibility?
A. Physical data center security  B. Hypervisor patching  C. Data and identity/access management  D. Network cabling

**55.** A mistake in a deployment template was copied to 300 servers in minutes. Which architecture feature made this possible?
A. Air gap  B. RTOS  C. Infrastructure as code  D. Cold site

**56.** Which component is the MOST valuable target in a software-defined network?
A. The data plane switches  B. Patch cables  C. The SDN controller (control plane)  D. User laptops

**57.** Which architecture runs short functions only when triggered, with no servers for the customer to manage?
A. Monolith  B. Mainframe  C. On-premises  D. Serverless

**58.** What is the main security drawback of containers compared with virtual machines?
A. They are slower to start  B. They share the host's kernel  C. They can't be scanned  D. They require a separate OS each

**59.** A water-treatment plant's control systems use old protocols and can't be taken offline for patching. These systems are BEST described as:
A. ICS/SCADA  B. SaaS  C. Serverless  D. Microservices

**60.** An air-gapped network was infected anyway. What was the MOST likely path?
A. Removable media  B. Public Wi-Fi  C. Its internet connection  D. A cloud API

**61.** A car's braking controller must respond within guaranteed milliseconds. It runs a(n):
A. RTOS  B. Hypervisor  C. SIEM  D. SDN controller

---

## Section H — Enterprise Infrastructure (Ch 30)

**62.** Where should a company place its public web servers?
A. Internal LAN  B. Screened subnet (DMZ)  C. Data center zone  D. Guest Wi-Fi

**63.** An IPS protecting a hospital network must not stop patient-care traffic if it fails. It should be configured to:
A. Fail-open  B. Fail-closed  C. Fail-secure  D. Shut down the network

**64.** In 802.1X, the network switch plays which role?
A. Supplicant  B. Authenticator  C. Authentication server  D. Certificate authority

**65.** Which EAP method requires certificates on both the client and the server?
A. EAP-TLS  B. PEAP  C. EAP-TTLS  D. EAP-FAST

**66.** Which IPsec protocol provides encryption?
A. ESP  B. AH  C. IKE  D. GRE

**67.** Administrators must connect to sensitive servers only through a single hardened, monitored host. This host is a:
A. Reverse proxy  B. Honeypot  C. Jump server  D. Load balancer

**68.** Which device spreads incoming web requests across several servers and stops sending traffic to failed ones?
A. TAP  B. IDS  C. Forward proxy  D. Load balancer

**69.** A small business wants one appliance combining firewall, IPS, antivirus, web filtering and VPN. Which fits BEST?
A. WAF  B. TAP  C. UTM  D. HSM

**70.** A company wants to combine SD-WAN with cloud-delivered security for branch offices and remote staff. Which solution fits?
A. SASE  B. RAID  C. PKI  D. NAT

**71.** An IDS connected to a SPAN port is BEST described as:
A. Passive, receiving a copy of traffic  B. Inline and active  C. Fail-closed  D. A forward proxy

---

## Section I — Protecting Data (Ch 31)

**72.** Call-center staff should see only the last four digits of card numbers. Which method?
A. Replication  B. Hashing  C. Steganography  D. Masking

**73.** Which method is NOT reversible?
A. Hashing  B. Tokenization  C. Encryption  D. Masking applied only on display

**74.** A law requires customer records to remain within national borders. Which method addresses this?
A. Hashing  B. Obfuscation  C. Geographic restrictions  D. Load balancing

**75.** Which tool blocks an employee from emailing a spreadsheet full of national ID numbers to a personal account?
A. UPS  B. DLP  C. SDN  D. OCSP

**76.** Developers need realistic test data without real customer identities. Which is BEST?
A. Snapshots  B. Replication  C. Static data masking  D. Journaling

**77.** Which statement about obfuscation is TRUE?
A. It is strong enough to use alone  B. It makes data hard to understand but should only be an extra layer  C. It is the same as encryption  D. It requires a CA

---

## Section J — Resilience & Recovery (Ch 32)

**78.** Which recovery site has hardware, software and near-live data ready to take over within minutes?
A. Cold site  B. Warm site  C. Hot site  D. Mobile site

**79.** A full backup runs Sunday and differential backups run Monday–Friday. After a crash on Friday evening (after Friday's backup), what is needed to restore?
A. Sunday full + all five differentials  B. Sunday full only  C. Friday's differential only  D. Sunday full + Friday's differential

**80.** Which provides instant power during an outage until a generator starts?
A. Load balancer  B. PDU  C. RAID 1  D. UPS

**81.** Managers discuss a ransomware scenario step by step in a meeting room, without touching systems. This is a:
A. Failover test  B. Parallel processing test  C. Tabletop exercise  D. Penetration test

**82.** Why isn't real-time replication alone sufficient protection against ransomware?
A. It is too slow  B. It also replicates the encrypted or corrupted data  C. It can't be encrypted  D. It only works on-premises

**83.** Which RAID level survives the failure of two disks?
A. RAID 0  B. RAID 1  C. RAID 5  D. RAID 6

**84.** A company uses firewalls from two different vendors so that one vendor's vulnerability can't defeat both layers. This is:
A. Multi-cloud  B. Platform diversity  C. Clustering  D. Journaling

**85.** Which is the BEST way to confirm that backups will work in a disaster?
A. Check the backup software's success emails  B. Use only snapshots  C. Buy more storage  D. Regularly perform test restores

---

## Section K — Change Management, Zero Trust & Deception (Ch 33)

**86.** A change caused an outage and must be reversed. Which part of change management provides the steps?
A. Impact analysis  B. Stakeholder list  C. Maintenance window  D. Backout plan

**87.** A database upgrade broke three applications that nobody had considered. Which step was done poorly?
A. Tabletop testing  B. Version control  C. Encryption  D. Impact analysis of dependencies

**88.** In a zero trust architecture, which component makes the decision to grant or deny access?
A. Policy Enforcement Point  B. Subject  C. Policy Engine  D. Implicit trust zone

**89.** Authentication requirements automatically increase when a user logs in from a new country on an unmanaged device. This is:
A. Adaptive identity  B. Implicit trust  C. Fail-open  D. Key escrow

**90.** A fake AWS access key is planted in a code repository and triggers an alert when anyone tries to use it. This is a:
A. Honeypot  B. Honeytoken  C. Honeynet  D. Honeyfile

---

## ✅ Answer Key

<details>
<summary><b>Click to show answers (try first!)</b></summary>

| # | Ans | Why (chapter) |
|---|---|---|
| 1 | C | Compromised MSP = supply chain (Ch 23) |
| 2 | D | Unneeded listening services = open service ports (Ch 23) |
| 3 | A | Factory logins = default credentials (Ch 23) |
| 4 | B | Isolate unsupported systems as a compensating control (Ch 23) |
| 5 | A | 802.1X blocks unauthenticated wired ports (Ch 23) |
| 6 | B | Malicious USB devices = removable device vector (Ch 23) |
| 7 | A | Attack surface = all entry points (Ch 23) |
| 8 | C | Client-based (agent installed on each device) (Ch 23) |
| 9 | D | SQL injection (Ch 24) |
| 10 | D | Parameterized queries / prepared statements (Ch 24) |
| 11 | D | Saved and served to every visitor = stored XSS (Ch 24) |
| 12 | B | Time-of-check to time-of-use race (Ch 24) |
| 13 | B | VM escape (Ch 24) |
| 14 | C | ASLR randomizes memory addresses (Ch 24) |
| 15 | B | Zero-day (Ch 24) |
| 16 | C | Misconfiguration (cloud-specific) (Ch 24) |
| 17 | B | Third-party library = software supply chain (Log4Shell) (Ch 24) |
| 18 | B | Spoofed source + bigger replies = reflected + amplified (Ch 25) |
| 19 | A | DNSSEC signs DNS answers (Ch 25) |
| 20 | B | ARP poisoning puts the attacker on-path (Ch 25) |
| 21 | D | Credential/session replay (Ch 25) |
| 22 | C | Same SSID impersonation = evil twin (Ch 25) |
| 23 | D | Unauthorized AP on the network = rogue AP (Ch 25) |
| 24 | D | HSTS forces HTTPS (Ch 25) |
| 25 | C | DNS tunneling (Ch 25) |
| 26 | C | `../` = directory traversal (Ch 26) |
| 27 | D | Few tries across many accounts = spraying (Ch 26) |
| 28 | B | Salting (Ch 26, 28) |
| 29 | D | Downgrade (Ch 26) |
| 30 | B | The user's browser is forged into acting = CSRF (Ch 26) |
| 31 | A | Impossible travel (Ch 26) |
| 32 | A | Cleared logs = missing logs (Ch 26) |
| 33 | C | User → SYSTEM = vertical (Ch 26) |
| 34 | D | RFID cloning (Ch 26) |
| 35 | A | Segmentation (Ch 27) |
| 36 | A | Application allow list (Ch 27) |
| 37 | A | Isolation (quarantine) (Ch 27) |
| 38 | B | Removing unnecessary software (Ch 27) |
| 39 | C | Configuration enforcement (Ch 27) |
| 40 | D | Sanitize storage, revoke credentials (Ch 27) |
| 41 | C | Least privilege (Ch 27) |
| 42 | B | Isolation/segmentation as compensating control (Ch 27) |
| 43 | C | TPM (Ch 28) |
| 44 | A | HSM (Ch 28) |
| 45 | B | OCSP (Ch 28) |
| 46 | A | Wildcard (Ch 28) |
| 47 | D | Public key + identity info (Ch 28) |
| 48 | D | Self-signed (Ch 28) |
| 49 | A | Tokenization (Ch 28, 31) |
| 50 | C | Key stretching (Ch 28) |
| 51 | B | Steganography (Ch 28) |
| 52 | B | Protect the root private key (Ch 28) |
| 53 | A | Provider patches the OS in PaaS (Ch 29) |
| 54 | C | Data and identity are always the customer's (Ch 29) |
| 55 | C | Infrastructure as code (Ch 29) |
| 56 | C | The SDN controller / control plane (Ch 29) |
| 57 | D | Serverless (Ch 29) |
| 58 | B | Shared kernel (Ch 29) |
| 59 | A | ICS/SCADA (Ch 29) |
| 60 | A | Removable media (e.g., Stuxnet) (Ch 29) |
| 61 | A | RTOS (Ch 29) |
| 62 | B | Screened subnet (Ch 30) |
| 63 | A | Fail-open favors availability (Ch 30) |
| 64 | B | Authenticator (Ch 30) |
| 65 | A | EAP-TLS (Ch 30) |
| 66 | A | ESP (Ch 30) |
| 67 | C | Jump server (Ch 30) |
| 68 | D | Load balancer (Ch 30) |
| 69 | C | UTM (Ch 30) |
| 70 | A | SASE (Ch 30) |
| 71 | A | Passive, copy of traffic (Ch 30) |
| 72 | D | Masking (Ch 31) |
| 73 | A | Hashing is one-way (Ch 31) |
| 74 | C | Geographic restrictions / sovereignty (Ch 31) |
| 75 | B | DLP (Ch 31) |
| 76 | C | Static data masking (Ch 31) |
| 77 | B | Obfuscation is only an extra layer (Ch 31) |
| 78 | C | Hot site (Ch 32) |
| 79 | D | Full + latest differential (Ch 32) |
| 80 | D | UPS (Ch 32) |
| 81 | C | Tabletop exercise (Ch 32) |
| 82 | B | Replication copies the damage too (Ch 32) |
| 83 | D | RAID 6 (double parity) (Ch 32) |
| 84 | B | Platform diversity (Ch 32) |
| 85 | D | Test restores (Ch 32) |
| 86 | D | Backout plan (Ch 33) |
| 87 | D | Impact analysis / dependencies (Ch 33) |
| 88 | C | Policy Engine (Ch 33) |
| 89 | A | Adaptive identity (Ch 33) |
| 90 | B | Honeytoken (Ch 33) |

**Scoring:**
- **81–90:** 🏆 Excellent. Domains 1–3 are strong. Start Level 4.
- **63–80:** ✅ Pass. Re-read the chapters behind your misses, then start Level 4.
- **50–62:** 🔁 Re-study your two weakest sections; retake in 4–5 days.
- **Below 50:** 📖 Re-read Chapters 24, 26, 28 and 30 (the most heavily tested in Domains 1–3), redo their checkpoints and labs, and retake in a week.

</details>
