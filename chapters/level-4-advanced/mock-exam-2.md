# 📝 Mock Exam 2

**90 questions · 90 minutes · Weighted like SY0-701 (D1: 11 · D2: 20 · D3: 16 · D4: 25 · D5: 18)**

Take this about a week after Mock Exam 1, once you've reviewed your mistakes. Same rules: real conditions, no notes, answer everything.

---

## Domain 1 — General Security Concepts

**1.** After a break-in, a guard reviews CCTV footage to identify the intruder. The footage is acting as which type of control?
A. Preventive  B. Directive  C. Detective  D. Compensating

**2.** A corrupted database is restored from last night's backup. Which control type is the restore?
A. Corrective  B. Deterrent  C. Preventive  D. Directive

**3.** Which of the following is a managerial control?
A. Annual risk assessment  B. Bollard  C. Firewall  D. Full-disk encryption

**4.** A company compares its current controls with ISO/IEC 27001 requirements to find what's missing. This is a:
A. Gap analysis  B. Penetration test  C. Tabletop exercise  D. Root cause analysis

**5.** In a zero trust model, authentication requirements become stricter when a user connects from an unmanaged device in a new country. This is:
A. Implicit trust  B. Key escrow  C. Threat scope reduction  D. Adaptive identity

**6.** A fake API key is planted in a code repository; any attempt to use it raises an alert. This is a:
A. Honeypot  B. Honeynet  C. Honeyfile  D. Honeytoken

**7.** Which part of change management schedules work for a time when users will be least affected?
A. Maintenance window  B. Backout plan  C. Ownership  D. Impact analysis

**8.** Every edit to the firewall configuration is tracked with author, date and reason, and earlier versions can be restored. This is:
A. Version control  B. Journaling  C. Key escrow  D. Tokenization

**9.** A secret message is hidden inside an audio file. Which technique is this?
A. Tokenization  B. Steganography  C. Data masking  D. Hashing

**10.** Which hostname is covered by a wildcard certificate for `*.example.com`?
A. example.com  B. mail.example.com  C. a.b.example.com  D. www.example.net

**11.** Which technique makes stolen password hashes much slower to crack?
A. Base64 encoding  B. Data masking  C. Compression  D. Key stretching (bcrypt, PBKDF2)

---

## Domain 2 — Threats, Vulnerabilities & Mitigations

**12.** A caller claiming to be the CEO's assistant pressures the help desk to reset the CEO's password "right now, before the board meeting." Which two principles are being used?
A. Scarcity and consensus  B. Consensus and intimidation  C. Familiarity and trust  D. Authority and urgency

**13.** A disgruntled administrator plants code that deletes backups if their account is ever disabled. This is a:
A. Worm  B. Logic bomb  C. Trojan  D. Spyware

**14.** Malware spreads to hundreds of hosts via a file-sharing protocol vulnerability, with no user interaction. This is a:
A. Virus  B. Keylogger  C. Logic bomb  D. Worm

**15.** Malware modifies the operating system kernel so antivirus can't see its files or processes. This is a:
A. Adware  B. Rootkit  C. Bloatware  D. Ransomware

**16.** A web log contains `GET /search?q=' UNION SELECT card_number FROM payments--`. Which attack is this?
A. XSS  B. Directory traversal  C. SQL injection  D. SSRF

**17.** A web app fetches any URL a user supplies; an attacker submits `http://169.254.169.254/latest/meta-data/`. Which attack is this?
A. CSRF  B. Replay  C. SSRF  D. Typosquatting

**18.** Logs show one failed login per account across 500 accounts, all using the password "Winter2026!". This is:
A. Brute force  B. Credential stuffing from one breach  C. Password spraying  D. A rainbow table attack

**19.** One user account logs in from Brazil and then from Germany within 15 minutes. Which indicator is this?
A. Blocked content  B. Out-of-cycle logging  C. Impossible travel  D. Missing logs

**20.** An attacker's access point broadcasts the same SSID as the corporate network. This is a(n):
A. Rogue AP  B. Evil twin  C. Jamming attack  D. Bluejacking

**21.** A server's CPU is constantly at 100% due to an unknown process mining cryptocurrency. Which indicator is this?
A. Published/documented  B. Account lockout  C. Impossible travel  D. Resource consumption

**22.** An attacker forces a TLS connection to use an old, weak cipher suite. This is a:
A. Collision attack  B. Birthday attack  C. Downgrade attack  D. Replay attack

**23.** An intruder forces open a locked rear door with a crowbar to reach the server room. Which type of attack is this?
A. Tailgating  B. RFID cloning  C. Environmental attack  D. Physical brute force

**24.** Attackers register `exampie.com` hoping users mistype `example.com`. This is:
A. DNS poisoning  B. Domain hijacking  C. Typosquatting  D. Pretexting

**25.** Attackers exploit a flaw that the software vendor doesn't yet know about. This is a:
A. Legacy vulnerability  B. Misconfiguration  C. Zero-day  D. Supply chain vulnerability

**26.** Memory from a deleted virtual machine is reassigned to a new VM without being wiped, exposing old data. This is:
A. VM escape  B. Resource reuse  C. VM sprawl  D. Side-loading

**27.** A profit-driven criminal group rents its ransomware to affiliates for a share of ransoms. Which threat actor is this?
A. Organized crime  B. Hacktivist  C. Insider threat  D. Unskilled attacker

**28.** New IP cameras still use the factory login admin/admin. What is the BEST hardening step?
A. Change the default passwords  B. Increase the camera resolution  C. Add more cameras  D. Enable UPnP

**29.** Users install apps on company phones from unofficial websites instead of the app store. This is:
A. Jailbreaking  B. Rooting  C. Tethering  D. Side-loading

**30.** A host makes thousands of DNS TXT queries with random-looking subdomains to one external domain. This MOST likely indicates:
A. A DHCP failure  B. DNS tunneling  C. NTP drift  D. Normal browsing

**31.** A finance clerk receives a phone call in the CFO's AI-cloned voice requesting an urgent wire transfer. This is:
A. Smishing  B. Typosquatting  C. A watering hole  D. Vishing

---

## Domain 3 — Security Architecture

**32.** In a SaaS model, who is responsible for managing which users can access the application?
A. The SaaS provider  B. The hardware vendor  C. The ISP  D. The customer

**33.** Which approach allows an entire environment to be rebuilt identically from version-controlled templates?
A. Air gapping  B. Infrastructure as code  C. Serverless only  D. Manual configuration

**34.** A network with no physical or wireless connection to any other network is:
A. Segmented with VLANs  B. Behind a NAT router  C. Air-gapped  D. Using SDN

**35.** A small office wants one appliance providing firewall, IPS, antivirus, content filtering and VPN. Which is BEST?
A. UTM  B. WAF  C. Load balancer  D. Jump server

**36.** Administrators must connect through a single hardened, logged host before managing servers. This host is a:
A. Jump server  B. Reverse proxy  C. Honeypot  D. Domain controller

**37.** An IDS receives a copy of traffic from a SPAN port. How is it deployed?
A. Inline, active  B. Fail-closed  C. Passive, monitor mode  D. As a proxy

**38.** Which EAP method requires certificates on both the client and the server?
A. PEAP  B. EAP-TLS  C. EAP-TTLS  D. EAP-FAST

**39.** A payment system replaces card numbers with random values; the real values are kept in a secure vault. This is:
A. Obfuscation  B. Hashing  C. Masking  D. Tokenization

**40.** Which method is one-way and is used to verify integrity?
A. Hashing  B. Encryption  C. Tokenization  D. Encoding

**41.** A backup copies only the data changed since the last backup of any type. Which backup is this?
A. Full  B. Differential  C. Snapshot  D. Incremental

**42.** What is the main risk of relying ONLY on real-time replication for ransomware recovery?
A. Replication also copies the encrypted or corrupted data  B. Replication is too expensive  C. Replication cannot cross sites  D. Replication requires tape

**43.** A database records every transaction in a separate log so that changes made since the last backup can be replayed after a crash. This is:
A. Snapshot  B. Differential backup  C. Journaling  D. Load balancing

**44.** A company runs workloads on two different cloud providers to survive a provider-wide outage. This is:
A. Platform diversity only  B. Multi-cloud  C. Clustering  D. Load balancing

**45.** Which RAID level mirrors data across two disks?
A. RAID 0  B. RAID 1  C. RAID 5  D. RAID 6

**46.** Which control BEST ensures data can't be read from a stolen laptop?
A. Full-disk encryption  B. Host-based firewall  C. Antivirus  D. Screen saver

**47.** Managers talk through a flood scenario step by step in a meeting room. Which test is this?
A. Failover  B. Parallel processing  C. Tabletop exercise  D. Simulation

---

## Domain 4 — Security Operations

**48.** Which tool shows Wi-Fi signal strength across a floor plan, revealing leakage into the parking lot?
A. NetFlow  B. Heat map from a site survey  C. SIEM dashboard  D. CVSS calculator

**49.** A company wants each employee to join the corporate Wi-Fi with their own directory account instead of a shared password. Which configuration is BEST?
A. WPA3-Enterprise with RADIUS (802.1X)  B. WPA3-Personal with a long passphrase  C. WPA2-Personal with MAC filtering  D. A hidden SSID with WEP

**50.** A BYOD phone is lost. How can the company remove corporate data without erasing personal photos?
A. Selective (container) wipe through MDM  B. Full device wipe  C. Degaussing  D. Jailbreaking

**51.** What does code signing provide?
A. Proof of the publisher and that the code wasn't modified  B. Confidentiality of the source code  C. Faster execution  D. Automatic patching

**52.** Which technique analyzes source code for flaws without running it?
A. DAST  B. SAST  C. Fuzzing  D. Penetration testing

**53.** A vendor shreds a company's old drives. Which document proves this was done?
A. SLA  B. Certificate of destruction  C. MOU  D. Chain of custody

**54.** Which scan type gives the MOST accurate view of installed patches?
A. Non-credentialed external scan  B. Port scan only  C. Ping sweep  D. Credentialed scan

**55.** Banks share threat intelligence through an industry group. This is a(n):
A. CASB  B. Bug bounty  C. ISAC (information-sharing organization)  D. SOAR platform

**56.** No patch is available, so the team adds a WAF rule blocking the exploit pattern. This is:
A. An exemption  B. Risk transfer  C. A compensating control  D. Decommissioning

**57.** After applying a patch, what should the team do to validate remediation?
A. Update the asset inventory  B. Close the ticket as soon as the patch installs  C. Lower the CVSS score  D. Rescan the system

**58.** Analysts ignore alerts because most are false positives. What is the BEST action?
A. Alert tuning  B. Increase log retention  C. Add more log sources  D. Archive old alerts

**59.** Which framework provides standardized, automated checking of systems against configuration benchmarks?
A. STIX  B. SCAP  C. SAML  D. SNMP

**60.** Which DNS record lists the IP addresses authorized to send email for a domain?
A. PTR  B. DKIM  C. DMARC  D. SPF

**61.** Which web filtering approach protects laptops even when they are off the corporate network?
A. Centralized proxy  B. Agent-based filtering  C. Router ACL  D. NAC

**62.** An administrator wants to disable USB storage on 5,000 Windows PCs at once. Which tool is BEST?
A. Group Policy  B. SELinux  C. NetFlow  D. Nmap

**63.** Which capability lets responders isolate an infected laptop from the network with one click?
A. FIM  B. DLP  C. EDR  D. Web filter

**64.** A system flags that an accountant downloaded 40 GB of files at 2 a.m., far above their normal behavior. Which technology is this?
A. RAID  B. SPF  C. User behavior analytics  D. OCSP

**65.** A website's "Sign in with Google" button returns an ID token describing the user. Which protocol provides this?
A. LDAP  B. TACACS+  C. OpenID Connect  D. Kerberos

**66.** Users suddenly can't authenticate to the Windows domain after a server's clock drifted 10 minutes. Which protocol is affected?
A. SNMP  B. SMTP  C. Kerberos  D. DHCP

**67.** All nurses receive the same access to patient charts because of their job. Which model is this?
A. MAC  B. DAC  C. ABAC  D. RBAC

**68.** Privileged account passwords are stored in a vault, checked out for each task, and rotated after use. This is:
A. Federation  B. Password vaulting  C. Attestation  D. SSO

**69.** Managers review and confirm their team members' access every quarter. This is:
A. Identity proofing  B. Escalation  C. Provisioning  D. Attestation (access review)

**70.** Old automation scripts that nobody understands keep breaking. This is BEST described as:
A. Employee retention  B. Workforce multiplier  C. Guard rails  D. Technical debt

**71.** After an incident is resolved, the team determines that an unpatched VPN appliance was the underlying reason the attacker got in. This activity is:
A. Containment  B. Threat hunting  C. Acquisition  D. Root cause analysis

**72.** Lawyers instruct the company to preserve all email related to a dispute. This is a:
A. Chain of custody  B. Legal hold  C. Data retention purge  D. Right to be forgotten

---

## Domain 5 — Security Program Management & Oversight

**73.** Which policy covers secure coding, code review and security testing?
A. AUP  B. SDLC policy  C. BC policy  D. Password standard

**74.** A multinational lets each regional office manage its own security within broad corporate rules. Which governance structure is this?
A. Centralized  B. Decentralized  C. Government entity  D. Audit committee

**75.** A company builds a record of every system that stores personal data: what it holds, why, who can access it and how long it is kept. This is BEST described as:
A. Legal hold  B. Data inventory and retention  C. Data masking  D. Right to be forgotten

**76.** The IT team performs backups and manages permissions for HR data. In this role they are the:
A. Data custodian  B. Data owner  C. Data controller  D. Data subject

**77.** An asset worth $500,000 has an exposure factor of 10% and an ARO of 0.2. What is the ALE?
A. $50,000  B. $10,000  C. $100,000  D. $5,000

**78.** What is the ARO for an event expected once every 25 years?
A. 25  B. 0.25  C. 4  D. 0.04

**79.** Which metric sets the maximum acceptable time to restore a service after a disruption?
A. RTO  B. RPO  C. MTBF  D. ALE

**80.** Which metric represents the average operating time between failures of a repairable system?
A. MTBF  B. MTTR  C. RPO  D. SLE

**81.** Management approves a temporary, documented deviation from the patching standard for one server until a set date. This is a(n):
A. Mitigation  B. Transfer  C. Avoidance  D. Exception

**82.** A company stops offering a risky online service to eliminate the risk. Which strategy is this?
A. Avoid  B. Accept  C. Transfer  D. Mitigate

**83.** Which agreement sets general terms that govern all future projects with a vendor?
A. SOW  B. MOU  C. MSA  D. NDA

**84.** Which document defines a specific project's tasks, deliverables and deadlines?
A. MSA  B. BPA  C. SOW/WO  D. SLA

**85.** Two companies agree to jointly sell a product and share profits and responsibilities. Which agreement fits?
A. NDA  B. BPA  C. MOU  D. SLA

**86.** Which provides the strongest independent assurance that a vendor's controls operated effectively over twelve months?
A. Vendor questionnaire  B. Vendor marketing brochure  C. SOC 2 Type II report  D. SOC 2 Type I report

**87.** Executives sign a formal statement that the company's financial controls are effective. This is:
A. Attestation  B. Acknowledgement  C. Self-assessment  D. E-discovery

**88.** After repeated compliance failures, a regulator revokes a money-transfer company's permit to operate. Which consequence of non-compliance is this?
A. Reputational damage  B. Contractual impacts  C. Fines  D. Loss of license

**89.** Before a penetration test begins, which document defines the systems in scope, the permitted testing hours and who to call if something breaks?
A. SLA  B. NDA  C. Rules of engagement  D. Chain of custody

**90.** An employee accidentally emails a customer spreadsheet to the wrong recipient. How is this behavior BEST classified?
A. Unintentional  B. Unexpected  C. Risky  D. Malicious

---

## ✅ Answer Key

<details>
<summary><b>Click to show answers (mark your exam first!)</b></summary>

| # | Ans | Domain | Why (chapter) |
|---|---|---|---|
| 1 | C | D1 | Reviewing footage = detective (13) |
| 2 | A | D1 | Restore = corrective (13) |
| 3 | A | D1 | Risk assessment = managerial (13) |
| 4 | A | D1 | Gap analysis (33) |
| 5 | D | D1 | Adaptive identity (33) |
| 6 | D | D1 | Fake credential used = honeytoken (33) |
| 7 | A | D1 | Maintenance window (33) |
| 8 | A | D1 | Version control (33) |
| 9 | B | D1 | Steganography (28) |
| 10 | B | D1 | Wildcard covers one subdomain level (28) |
| 11 | D | D1 | Key stretching (28) |
| 12 | D | D2 | Authority + urgency (15) |
| 13 | B | D2 | Logic bomb (16) |
| 14 | D | D2 | Worm (16) |
| 15 | B | D2 | Rootkit (16) |
| 16 | C | D2 | SQL injection (24) |
| 17 | C | D2 | SSRF to cloud metadata (26) |
| 18 | C | D2 | One password, many accounts = spraying (26) |
| 19 | C | D2 | Impossible travel (26) |
| 20 | B | D2 | Evil twin (25) |
| 21 | D | D2 | Resource consumption (26) |
| 22 | C | D2 | Downgrade (26) |
| 23 | D | D2 | Forcing a lock or door = physical brute force (19, 26) |
| 24 | C | D2 | Typosquatting (15) |
| 25 | C | D2 | Zero-day (24) |
| 26 | B | D2 | Resource reuse (24) |
| 27 | A | D2 | Organized crime (RaaS) (14) |
| 28 | A | D2 | Change default passwords (27) |
| 29 | D | D2 | Side-loading (24) |
| 30 | B | D2 | DNS tunneling (25) |
| 31 | D | D2 | Voice = vishing (15, 23) |
| 32 | D | D3 | Identity/access is always the customer's (29) |
| 33 | B | D3 | Infrastructure as code (29) |
| 34 | C | D3 | Air gap (29) |
| 35 | A | D3 | UTM (30) |
| 36 | A | D3 | Jump server (30) |
| 37 | C | D3 | Passive/monitor (30) |
| 38 | B | D3 | EAP-TLS (30) |
| 39 | D | D3 | Tokenization (31) |
| 40 | A | D3 | Hashing (31) |
| 41 | D | D3 | Incremental (32) |
| 42 | A | D3 | Replication copies the damage (32) |
| 43 | C | D3 | Journaling (32) |
| 44 | B | D3 | Multi-cloud (32) |
| 45 | B | D3 | RAID 1 (32) |
| 46 | A | D3 | Full-disk encryption (28, 31) |
| 47 | C | D3 | Tabletop (32) |
| 48 | B | D4 | Heat map / site survey (34) |
| 49 | A | D4 | Per-user Wi-Fi logins = WPA3-Enterprise + RADIUS (34) |
| 50 | A | D4 | Selective wipe (34) |
| 51 | A | D4 | Code signing (34) |
| 52 | B | D4 | SAST (34, 36) |
| 53 | B | D4 | Certificate of destruction (35) |
| 54 | D | D4 | Credentialed scan (36) |
| 55 | C | D4 | ISAC (36) |
| 56 | C | D4 | Compensating control / virtual patch (36) |
| 57 | D | D4 | Rescan (36) |
| 58 | A | D4 | Alert tuning (37) |
| 59 | B | D4 | SCAP (37) |
| 60 | D | D4 | SPF (38) |
| 61 | B | D4 | Agent-based filtering (38) |
| 62 | A | D4 | Group Policy (38) |
| 63 | C | D4 | EDR (38) |
| 64 | C | D4 | UBA (38) |
| 65 | C | D4 | OpenID Connect (39) |
| 66 | C | D4 | Kerberos needs synchronized clocks (39) |
| 67 | D | D4 | RBAC (39) |
| 68 | B | D4 | Password vaulting (39) |
| 69 | D | D4 | Attestation / access review (39) |
| 70 | D | D4 | Technical debt (40) |
| 71 | D | D4 | Finding the underlying cause = root cause analysis (41) |
| 72 | B | D4 | Legal hold (41) |
| 73 | B | D5 | SDLC policy (43) |
| 74 | B | D5 | Regions manage their own = decentralized (43) |
| 75 | B | D5 | Data inventory and retention (46) |
| 76 | A | D5 | Custodian (43) |
| 77 | B | D5 | 500,000 × 0.1 = 50,000; × 0.2 = 10,000 (44) |
| 78 | D | D5 | 1 ÷ 25 = 0.04 (44) |
| 79 | A | D5 | RTO (44) |
| 80 | A | D5 | MTBF (44) |
| 81 | D | D5 | Exception (44) |
| 82 | A | D5 | Avoid (44) |
| 83 | C | D5 | MSA (45) |
| 84 | C | D5 | SOW/WO (45) |
| 85 | B | D5 | BPA (45) |
| 86 | C | D5 | SOC 2 Type II (45, 47) |
| 87 | A | D5 | Attestation (46, 47) |
| 88 | D | D5 | Permit revoked = loss of license (46) |
| 89 | C | D5 | Rules of engagement (45, 47) |
| 90 | A | D5 | Unintentional (48) |

**Scoring:** 77+ (85%) = ready-level performance · 63–76 = keep going, focus on your weakest domain · below 63 = re-study your two weakest domains before Mock 3.

</details>
