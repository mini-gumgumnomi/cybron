# 📝 Mock Exam 3

**90 questions · 90 minutes · Weighted like SY0-701 (D1: 11 · D2: 20 · D3: 16 · D4: 25 · D5: 18)**

Your final readiness check, about two days before the real exam. Real conditions. Aim for **85%+** with no domain below 75%.

---

## Domain 1 — General Security Concepts

**1.** A router ACL blocks all Telnet traffic. What are its category and type?
A. Managerial, detective  B. Physical, deterrent  C. Technical, preventive  D. Operational, corrective

**2.** Which of the following is a directive control?
A. Fire extinguisher  B. A backup generator  C. An IDS  D. A policy requiring employees to wear visible ID badges

**3.** The security team runs monthly phishing-awareness sessions that all employees attend. Which control category is this?
A. Operational  B. Technical  C. Physical  D. Managerial

**4.** Before IoT sensors may send readings to a central server, each sensor must prove its identity. Which is the BEST approach?
A. Device certificates  B. A shared Wi-Fi password  C. MAC address filtering  D. A hidden SSID

**5.** After logging in successfully, a user is denied access to the payroll folder. Which AAA function denied access?
A. Authorization  B. Authentication  C. Identification  D. Accounting

**6.** In a zero trust architecture, which plane contains the Policy Engine and Policy Administrator that make and manage access decisions?
A. Data plane  B. Control plane  C. Implicit trust zone  D. Management VLAN

**7.** A security team deploys a network of decoy servers and workstations that imitates a real department. This is a:
A. Honeyfile  B. Honeytoken  C. Sandbox  D. Honeynet

**8.** A change requires restarting the email service for five minutes. Which technical implication must be communicated to users?
A. Version control  B. Downtime  C. Legacy application  D. Allow list update

**9.** What does a certificate signing request (CSR) contain?
A. The applicant's private key  B. A CRL  C. The CA's private key  D. The applicant's public key and identity details

**10.** In a certificate chain, what serves as the root of trust?
A. The leaf certificate  B. The OCSP responder  C. The intermediate CA's CSR  D. The root CA certificate in the trust store

**11.** Why is a blockchain ledger tamper-evident?
A. It uses steganography  B. It is encrypted with AES  C. It is stored on one central server  D. Each block contains the hash of the previous block

---

## Domain 2 — Threats, Vulnerabilities & Mitigations

**12.** An email to one employee mentions the conference she attended last week and includes a "slides" link. This is BEST described as:
A. Vishing  B. Smishing  C. Spear phishing  D. Typosquatting

**13.** A supplier's real, compromised mailbox is used to ask the accounts team to change the supplier's bank details. This is:
A. Bluejacking  B. A watering hole  C. Brand impersonation only  D. Business email compromise

**14.** A free game download secretly installs a backdoor. This malware is a:
A. Worm  B. Logic bomb  C. Trojan  D. Rootkit only

**15.** Which control BEST limits the damage if a keylogger steals users' passwords?
A. Longer passwords  B. Password expiration every 30 days  C. Multifactor authentication  D. Password hints

**16.** Thousands of compromised IoT devices are controlled through a C2 server to launch DDoS attacks. They form a:
A. Honeynet  B. Cluster  C. VLAN  D. Botnet

**17.** Which OS protection marks memory regions as non-executable, making buffer-overflow exploits harder?
A. SPF  B. HSTS  C. DNSSEC  D. DEP/NX

**18.** A program checks a file's permissions, but an attacker replaces the file before the program opens it. This is:
A. A race condition (TOC/TOU)  B. A collision  C. A downgrade  D. SSRF

**19.** A web request contains `%2e%2e%2f%2e%2e%2fetc%2fpasswd`. Which attack is MOST likely?
A. SQL injection  B. CSRF  C. Directory traversal  D. XSS

**20.** Which control BEST prevents CSRF attacks?
A. Anti-CSRF tokens  B. Disk encryption  C. RAID  D. Port security

**21.** Which control BEST stops online brute-force attempts against a single account?
A. Data masking  B. Account lockout with MFA  C. Steganography  D. Load balancing

**22.** Users who type the correct address for their bank are sent to a fake site because the company's DNS resolver has cached a forged record. This is:
A. DNS poisoning  B. Typosquatting  C. Domain hijacking  D. DNS tunneling

**23.** Which control BEST mitigates RFID badge cloning?
A. Brighter lighting  B. Encrypted smart cards or badge plus PIN  C. Longer passwords  D. A bigger fence

**24.** An ARP table shows two different IP addresses mapped to the same MAC address, one of them the gateway. This suggests:
A. A DHCP lease renewal  B. ARP poisoning (on-path attack)  C. Normal behavior  D. DNSSEC failure

**25.** Which control BEST prevents replay attacks?
A. Disabling logging  B. Larger hard drives  C. Timestamps and nonces  D. Port mirroring

**26.** Lobby kiosks run an operating system that the vendor stopped supporting two years ago. Which vulnerability is this?
A. Unsupported (end-of-life) system  B. Zero-day  C. Race condition  D. Memory injection

**27.** A phone has been jailbroken to install unapproved apps. Which vulnerability category is this?
A. Mobile device  B. Cryptographic  C. Firmware  D. Virtualization

**28.** Cloud access keys are found in a public code repository. Which vulnerability category BEST fits?
A. Firmware  B. Cloud-specific (exposed credentials)  C. Race condition  D. Buffer overflow

**29.** Users suddenly cannot open their files, and a ransom note appears. Which indicator is this?
A. Impossible travel  B. Resource inaccessibility  C. Out-of-cycle logging  D. Concurrent session usage

**30.** An unused server from a finished project is still running and unpatched. What is the BEST action?
A. Add it to the monthly patch cycle  B. Move it to a separate VLAN  C. Install EDR on it  D. Decommission it securely

**31.** Servers repeatedly drift from the approved security settings. Which mitigation BEST addresses this?
A. Job rotation  B. Steganography  C. Tokenization  D. Configuration enforcement

---

## Domain 3 — Security Architecture

**32.** In a PaaS model, which is the customer's responsibility?
A. Securing the application code and data  B. Patching the operating system  C. Physical data center security  D. Hypervisor maintenance

**33.** What is a key security drawback of a microservices architecture?
A. More APIs and connections create a larger attack surface  B. One bug always crashes everything  C. It cannot scale  D. It cannot use containers

**34.** For ICS/SCADA systems, which security priorities usually come first?
A. Confidentiality and secrecy  B. Anonymity  C. Non-repudiation  D. Availability and safety

**35.** Which property defines a real-time operating system?
A. A graphical interface  B. Guaranteed, deterministic response times  C. Cloud hosting  D. Container support

**36.** What is the main weakness of a centralized architecture?
A. Inconsistent security policies  B. Too many local administrators  C. A single point of failure  D. Impossible to monitor

**37.** A load balancer keeps each user on the same web server for their whole session. This feature is:
A. Clustering  B. Fail-open  C. Persistence (sticky sessions)  D. Round-robin

**38.** Which device sits between employees and the internet, inspecting and filtering their outbound web requests?
A. Forward proxy  B. Reverse proxy  C. Load balancer  D. Jump server

**39.** What can a Layer 7 firewall do that a Layer 4 firewall cannot?
A. Filter by IP address  B. Allow an application but block specific functions within it  C. Filter by port  D. Route packets

**40.** Which server belongs in a screened subnet?
A. The domain controller  B. The public web server  C. The HR database  D. The backup vault

**41.** Remote users need a VPN that works through most hotel firewalls over port 443. Which is BEST?
A. PPTP  B. IPsec AH only  C. Telnet tunnel  D. SSL/TLS VPN

**42.** Why should backup sites be geographically dispersed?
A. To avoid encryption  B. To reduce licensing costs  C. So one disaster can't affect both sites  D. To speed up local restores

**43.** Why is a VM snapshot alone NOT a sufficient backup strategy?
A. Snapshots are usually stored on the same system as the original  B. Snapshots can't be restored  C. Snapshots are always encrypted  D. Snapshots require tape

**44.** With a full backup on Sunday and differential backups each night, what's needed to restore after a crash on Thursday morning?
A. Sunday full + Monday, Tuesday and Wednesday differentials  B. Wednesday's differential only  C. Sunday full + Wednesday's differential  D. Sunday full only

**45.** What role does a generator play in power resilience?
A. Provides instant power for seconds  B. Replaces the UPS entirely  C. Filters network traffic  D. Provides long-term power as long as fuel lasts

**46.** Ensuring enough trained staff will be available during a disaster is part of:
A. Capacity planning (people)  B. Platform diversity  C. Journaling  D. Tokenization

**47.** Data classified as "critical" is primarily protected for which goal?
A. Obfuscation  B. Anonymity  C. Non-repudiation  D. Availability

---

## Domain 4 — Security Operations

**48.** Which is a hardening step for network switches?
A. Disable unused ports  B. Enable Telnet for remote management  C. Allow all VLANs on every port  D. Keep the default management credentials

**49.** Which authentication method does WPA3-Personal use?
A. PSK with TKIP  B. SAE  C. WEP  D. EAP-TLS

**50.** Where must input validation be enforced to be effective?
A. Only in the browser  B. On the server side  C. Only in the firewall  D. In the DNS server

**51.** An email gateway opens suspicious attachments in an isolated environment to watch their behavior. This is:
A. Clustering  B. Tokenization  C. Sandboxing  D. Steganography

**52.** Each server in the inventory lists the person responsible for its upkeep and security decisions. Which asset management activity is this?
A. Assigning ownership  B. Enumeration  C. Sanitization  D. Certification

**53.** Which policy defines how long data must be kept before secure disposal?
A. Change management policy  B. AUP  C. Data retention policy  D. Password standard

**54.** Which identification method alerts when a third-party library used by your application has a known vulnerability?
A. Package monitoring  B. Penetration testing  C. Tabletop exercise  D. Dark web monitoring

**55.** A company pays external researchers for each valid vulnerability they report. This is a:
A. Red team contract  B. Bug bounty program  C. SOC 2 audit  D. Questionnaire

**56.** A vulnerability has a CVSS base score of 5.5. Which severity band is this?
A. Low  B. Medium  C. High  D. Critical

**57.** Two servers have the same vulnerability with a CVSS base score of 7.5. One is internet-facing; the other sits on an isolated lab network. Why should the internet-facing server be patched FIRST?
A. Its CVSS base score is higher  B. Lab systems never need patches  C. Environmental variables such as exposure raise its real-world risk  D. It has a different CVE ID

**58.** Logs must be kept for seven years for compliance. Which monitoring activity is this?
A. Archiving  B. Alert tuning  C. Quarantine  D. Scanning

**59.** What is an advantage of agentless monitoring?
A. Nothing to install or maintain on endpoints  B. Deepest possible visibility  C. Works on devices with no network connectivity  D. Always real-time

**60.** What does DKIM verify?
A. That the sending server's IP is authorized  B. The DMARC policy  C. The receiver's identity  D. A digital signature showing the message came from the domain and was not altered

**61.** Which control blocks malware C2 domains for every device using the corporate resolver, without installing agents?
A. FIM  B. DNS filtering  C. HIPS  D. MDM

**62.** A web filter blocks a newly registered domain with no history. Which feature is this?
A. SPF  B. Content categorization  C. Reputation  D. Static analysis

**63.** Which technology correlates detections across endpoints, network, email, cloud and identity?
A. EDR  B. XDR  C. HIPS  D. DLP

**64.** Staff at a partner organization access a shared portal using their own organization's credentials. This is:
A. Federation  B. Shadow IT  C. Tokenization  D. Key escrow

**65.** Access is allowed only if the user is in HR, using a managed laptop, during business hours, from the office network. Which model is this?
A. DAC  B. ABAC  C. MAC  D. Rule-based only

**66.** A temporary credential is created for a single administrative task and expires immediately after. This is:
A. Shared accounts  B. Password reuse  C. Ephemeral credentials  D. Default credentials

**67.** What should happen to an employee's accounts on their last day?
A. Make them read-only forever  B. Keep them active for a month  C. Transfer the password to a colleague  D. Disable them immediately

**68.** A SOAR playbook automatically removes a reported phishing email from all mailboxes within seconds. Which benefit is MOST demonstrated?
A. Single point of failure  B. Technical debt  C. Reaction time  D. Complexity

**69.** Unacknowledged critical alerts are automatically sent to the on-call manager after 15 minutes. This automation use case is:
A. Security groups  B. Guard rails  C. Resource provisioning  D. Escalation

**70.** What is the main purpose of the lessons learned phase?
A. Improve future prevention and response  B. Remove malware  C. Restore backups  D. Detect the attack

**71.** Analysts search for signs of compromise based on a hypothesis, without any alert. This is:
A. Threat hunting  B. Incident containment  C. Vulnerability scanning  D. E-discovery

**72.** The legal process of identifying, collecting and producing electronic records for a lawsuit is:
A. Attestation  B. Chain of custody  C. Acquisition  D. E-discovery

---

## Domain 5 — Security Program Management & Oversight

**73.** Which procedure covers collecting badges and devices and revoking access when someone leaves?
A. Onboarding  B. Offboarding  C. Change management  D. Playbook for phishing

**74.** PCI DSS is BEST categorized as which type of external consideration?
A. Industry  B. Local  C. National law  D. Regional

**75.** Which body holds ultimate accountability for an organization's security strategy and risk appetite?
A. The data processor  B. The help desk  C. The board of directors  D. The penetration tester

**76.** Rating risks as low, medium or high is which type of analysis?
A. Quantitative  B. Qualitative  C. Statistical sampling  D. Cost-benefit

**77.** A risk has an ALE of $20,000 and an SLE of $80,000. What is the ARO?
A. 4  B. 2.5  C. 0.4  D. 0.25

**78.** In a risk register, who is the risk owner?
A. The auditor  B. The attacker  C. The person accountable for managing that risk  D. The insurer

**79.** The board rules that any risk with a potential loss above $250,000 must be escalated to it before anyone may accept it. This sets a:
A. Risk register entry  B. Risk threshold  C. Exposure factor  D. Residual risk

**80.** What is residual risk?
A. Risk before any controls  B. Risk remaining after controls are applied  C. Risk transferred to insurers  D. Risk from vendors only

**81.** Which metric measures the average time needed to repair a failed system?
A. MTBF  B. ARO  C. RPO  D. MTTR

**82.** Investigating a vendor's financial stability, security and breach history before signing is:
A. Due care  B. Due diligence  C. Attestation  D. E-discovery

**83.** The person choosing between vendors owns shares in one of them. This is a:
A. Supply chain analysis  B. Right-to-audit issue  C. Conflict of interest  D. Service level breach

**84.** Before sharing network diagrams with a consultant, which agreement should be signed?
A. NDA  B. BPA  C. SLA  D. MOU

**85.** What is the main limitation of vendor security questionnaires?
A. They're illegal in the EU  B. They are too technical to read  C. Answers are self-reported and may be inaccurate  D. They replace contracts

**86.** A GRC platform continuously checks cloud configurations against compliance rules. This is:
A. E-discovery  B. A self-assessment interview  C. Compliance automation  D. A tabletop exercise

**87.** Under GDPR, within how many hours must a qualifying personal data breach be reported to the supervisory authority?
A. 24  B. 48  C. 72  D. 168

**88.** Which board-level group oversees internal and external audits independently of management?
A. Help desk  B. Change Advisory Board  C. Red team  D. Audit committee

**89.** A tester attempts to tailgate into the data center and clone employee badges. This is which type of penetration test?
A. Defensive  B. Physical  C. Integrated  D. Passive reconnaissance

**90.** Employees are taught not to post photos of their badges or office layouts on social media. Which training topic is this?
A. Hybrid work  B. Password management  C. Removable media  D. Operational security (OPSEC)

---

## ✅ Answer Key

<details>
<summary><b>Click to show answers (mark your exam first!)</b></summary>

| # | Ans | Domain | Why (chapter) |
|---|---|---|---|
| 1 | C | D1 | Technical, preventive (13) |
| 2 | D | D1 | Policy telling people what to do = directive (13) |
| 3 | A | D1 | People carrying out training = operational (13) |
| 4 | A | D1 | Authenticating systems with certificates (12) |
| 5 | A | D1 | Authorization (12) |
| 6 | B | D1 | Control plane = the decision-maker (33) |
| 7 | D | D1 | Honeynet (33) |
| 8 | B | D1 | Downtime (33) |
| 9 | D | D1 | Public key + identity (28) |
| 10 | D | D1 | Root CA certificate (28) |
| 11 | D | D1 | Hash-linked blocks (28) |
| 12 | C | D2 | Targeted = spear phishing (15) |
| 13 | D | D2 | BEC (15) |
| 14 | C | D2 | Trojan (16) |
| 15 | C | D2 | MFA (17) |
| 16 | D | D2 | Botnet (16) |
| 17 | D | D2 | DEP/NX (24) |
| 18 | A | D2 | TOC/TOU (24) |
| 19 | C | D2 | Encoded `../` = directory traversal (26) |
| 20 | A | D2 | Anti-CSRF tokens (26) |
| 21 | B | D2 | Lockout + MFA (26) |
| 22 | A | D2 | Forged record in resolver cache = DNS poisoning (25) |
| 23 | B | D2 | Encrypted cards / badge + PIN (19, 26) |
| 24 | B | D2 | ARP poisoning (25) |
| 25 | C | D2 | Nonces/timestamps (25) |
| 26 | A | D2 | Unsupported system (23, 24) |
| 27 | A | D2 | Mobile device vulnerability (24) |
| 28 | B | D2 | Cloud-specific (24) |
| 29 | B | D2 | Resource inaccessibility (26) |
| 30 | D | D2 | Unused system = decommission, not maintain (27) |
| 31 | D | D2 | Configuration enforcement (27) |
| 32 | A | D3 | PaaS: customer owns app and data (29) |
| 33 | A | D3 | More APIs = more attack surface (29) |
| 34 | D | D3 | Availability & safety (29) |
| 35 | B | D3 | Deterministic timing (29) |
| 36 | C | D3 | Single point of failure (29) |
| 37 | C | D3 | Persistence (30) |
| 38 | A | D3 | Forward proxy (30) |
| 39 | B | D3 | Application awareness (30) |
| 40 | B | D3 | Public web server (30) |
| 41 | D | D3 | SSL/TLS VPN over 443 (30) |
| 42 | C | D3 | Geographic dispersion (32) |
| 43 | A | D3 | Same-system storage (32) |
| 44 | C | D3 | Full + latest differential (32) |
| 45 | D | D3 | Long-term power (32) |
| 46 | A | D3 | Capacity planning: people (32) |
| 47 | D | D3 | Critical = availability (21) |
| 48 | A | D4 | Disable unused ports (34) |
| 49 | B | D4 | SAE (34) |
| 50 | B | D4 | Server-side (34) |
| 51 | C | D4 | Sandboxing (34) |
| 52 | A | D4 | Assignment/accounting: ownership (35) |
| 53 | C | D4 | Data retention (35) |
| 54 | A | D4 | Package monitoring (36) |
| 55 | B | D4 | Bug bounty (36) |
| 56 | B | D4 | 4.0–6.9 = Medium (36) |
| 57 | C | D4 | Environmental variables (exposure) drive priority (36) |
| 58 | A | D4 | Archiving (37) |
| 59 | A | D4 | Nothing to install (37) |
| 60 | D | D4 | DKIM signature (38) |
| 61 | B | D4 | DNS filtering (38) |
| 62 | C | D4 | Reputation (38) |
| 63 | B | D4 | XDR (38) |
| 64 | A | D4 | Federation (39) |
| 65 | B | D4 | ABAC (39) |
| 66 | C | D4 | Ephemeral credentials (39) |
| 67 | D | D4 | De-provision immediately (39) |
| 68 | C | D4 | Reaction time (40) |
| 69 | D | D4 | Escalation (40) |
| 70 | A | D4 | Lessons learned (41) |
| 71 | A | D4 | Threat hunting (41) |
| 72 | D | D4 | E-discovery (41) |
| 73 | B | D5 | Offboarding (43) |
| 74 | A | D5 | Industry (43) |
| 75 | C | D5 | Board (43) |
| 76 | B | D5 | Qualitative (44) |
| 77 | D | D5 | 20,000 ÷ 80,000 = 0.25 (44) |
| 78 | C | D5 | Risk owner (44) |
| 79 | B | D5 | Escalation trigger level = risk threshold (44) |
| 80 | B | D5 | Residual risk (44) |
| 81 | D | D5 | MTTR (44) |
| 82 | B | D5 | Due diligence (45) |
| 83 | C | D5 | Conflict of interest (45) |
| 84 | A | D5 | NDA (45) |
| 85 | C | D5 | Self-reported (45) |
| 86 | C | D5 | Compliance automation (46) |
| 87 | C | D5 | 72 hours (46) |
| 88 | D | D5 | Audit committee (47) |
| 89 | B | D5 | Physical pentest (47) |
| 90 | D | D5 | OPSEC (48) |

**Scoring:** 77+ (85%) on this mock **and** Mock 2 → you're ready to book · 63–76 → spend 3–5 more days on weak domains, then retake a mock · below 63 → postpone the exam and re-study your weakest domains.

</details>
