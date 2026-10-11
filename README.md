# Cybron — *From Zero to Security+*

A beginner-first, figure-heavy book for passing the **CompTIA Security+ (SY0-701)** exam. It starts from "what is a computer?" and finishes at full exam readiness. AI/LLM security is covered in an appendix, so the book is also ready for the coming **SY0-801** update.

## The four levels

| Level | Name | Chapters | Status |
|---|---|---|---|
| 🧱 1 | Basic Foundation to Understand to Start | 1–11 + Gate Test | ✅ Written |
| 🌱 2 | Beginner for Exam | 12–22 + Gate Test | ✅ Written |
| 📈 3 | Can Score ~40% in Exam | 23–33 + Gate Test | ✅ Written |
| 🏆 4 | Advanced Knowledge — 100% Exam Pass | 34–51 + 3 Mock Exams | ✅ Written |

📘 **[Full Book Plan](BOOK_PLAN.md)**: every chapter, topic, figure, study schedule, and a map from each exam objective to its chapter.

## 🧱 Level 1 — Basic Foundation to Understand to Start

| # | Chapter | You will learn |
|---|---|---|
| 1 | [What Is a Computer?](chapters/level-1-foundation/01-what-is-a-computer.md) | CPU, RAM, storage, firmware, TPM, bits & bytes |
| 2 | [Software, Operating Systems & Files](chapters/level-1-foundation/02-software-operating-systems-files.md) | OS, processes, files, permissions, least privilege, patching, Secure Boot |
| 3 | [How Computers Represent Data](chapters/level-1-foundation/03-how-computers-represent-data.md) | Binary, hex, ASCII, encoding vs encryption vs hashing |
| 4 | [Networking 101](chapters/level-1-foundation/04-networking-101.md) | MAC & IP addresses, subnets, NAT, routers & switches, ARP |
| 5 | [Network Models: OSI & TCP/IP](chapters/level-1-foundation/05-osi-and-tcp-ip-models.md) | 7 layers, encapsulation, TCP vs UDP, handshake, ports |
| 6 | [Network Services, Protocols & Ports](chapters/level-1-foundation/06-network-services-protocols-ports.md) | DNS, DHCP, HTTPS, email, master port table, secure replacements |
| 7 | [Wireless & Mobile Basics](chapters/level-1-foundation/07-wireless-and-mobile-basics.md) | Wi-Fi, WEP→WPA3, Bluetooth, NFC, RFID, cellular, mobile risks |
| 8 | [Servers, Virtualization & Cloud](chapters/level-1-foundation/08-servers-virtualization-cloud.md) | Data centers, hypervisors, containers, IaaS/PaaS/SaaS, shared responsibility |
| 9 | [The Command Line](chapters/level-1-foundation/09-the-command-line.md) | ping, tracert, ipconfig, nslookup, netstat, Nmap, Wireshark, home lab |
| 10 | [What Is Cybersecurity?](chapters/level-1-foundation/10-what-is-cybersecurity.md) | Threat, vulnerability, risk, CIA, kill chain, real incidents, careers |
| 11 | [The Exam & How to Study](chapters/level-1-foundation/11-exam-and-study-skills.md) | Format, scoring, question traps, study system |
| ✅ | [Level 1 Gate Test](chapters/level-1-foundation/level-1-gate-test.md) | 50 questions: score 80% to move on |

## 🌱 Level 2 — Beginner for Exam

| # | Chapter | You will learn |
|---|---|---|
| 12 | [The CIA Triad, Non-Repudiation & AAA](chapters/level-2-beginner/12-cia-triad-and-aaa.md) | Confidentiality, integrity, availability; authentication vs authorization vs accounting |
| 13 | [Security Controls](chapters/level-2-beginner/13-security-controls.md) | 4 categories × 6 types: the control grid |
| 14 | [Threat Actors & Motivations](chapters/level-2-beginner/14-threat-actors-and-motivations.md) | Nation-states, organized crime, hacktivists, insiders, shadow IT; APTs |
| 15 | [Social Engineering](chapters/level-2-beginner/15-social-engineering.md) | Phishing family, BEC, pretexting, watering hole, typosquatting; spotting red flags |
| 16 | [The Malware Zoo](chapters/level-2-beginner/16-malware-zoo.md) | Virus vs worm, trojan, rootkit, logic bomb, ransomware, botnets, fileless |
| 17 | [Passwords, Authentication & MFA](chapters/level-2-beginner/17-passwords-authentication-mfa.md) | Factors, MFA, passkeys, password best practice, FAR/FRR/CER |
| 18 | [Cryptography Made Simple](chapters/level-2-beginner/18-cryptography-made-simple.md) | Symmetric vs asymmetric, hashing, digital signatures, which key to use |
| 19 | [Physical Security](chapters/level-2-beginner/19-physical-security.md) | Bollards, vestibules, badges, guards, sensors, tailgating |
| 20 | [Defense in Depth & First Tools](chapters/level-2-beginner/20-defense-in-depth-first-tools.md) | Firewalls, IDS/IPS, WAF, VPN, EDR, SIEM, honeypots, segmentation |
| 21 | [Data Basics](chapters/level-2-beginner/21-data-basics.md) | Data types, classification, at rest / in transit / in use, sovereignty |
| 22 | [Policies, Risk & Compliance](chapters/level-2-beginner/22-policies-risk-compliance-intro.md) | Policy vs standard vs procedure; accept/avoid/transfer/mitigate; GDPR, HIPAA, PCI DSS |
| ✅ | [Level 2 Gate Test](chapters/level-2-beginner/level-2-gate-test.md) | 75 questions: score 75% to move on |

## 📈 Level 3 — Can Score ~40% in Exam

| # | Chapter | You will learn |
|---|---|---|
| 23 | [Threat Vectors & Attack Surfaces](chapters/level-3-intermediate/23-threat-vectors-attack-surfaces.md) | Every path in: messages, files, USB, open ports, default credentials, supply chain |
| 24 | [Vulnerability Types](chapters/level-3-intermediate/24-vulnerability-types.md) | Buffer overflow, race conditions, SQLi, XSS, VM escape, misconfiguration, zero-day |
| 25 | [Network Attacks & Indicators](chapters/level-3-intermediate/25-network-attacks-indicators.md) | Reflected/amplified DDoS, DNS attacks, evil twin, on-path, replay |
| 26 | [Application, Password & Crypto Attacks + Indicators](chapters/level-3-intermediate/26-application-password-crypto-attacks-indicators.md) | CSRF/SSRF, traversal, spraying, downgrade, birthday; the 9 indicators |
| 27 | [Mitigation & Hardening](chapters/level-3-intermediate/27-mitigation-hardening.md) | Segmentation, isolation, allow lists, configuration enforcement, hardening |
| 28 | [PKI, Certificates & Applied Crypto](chapters/level-3-intermediate/28-pki-certificates-applied-crypto.md) | CAs, CSR, CRL/OCSP, wildcard, TPM/HSM/enclave, salting, tokenization, blockchain |
| 29 | [Architecture Models](chapters/level-3-intermediate/29-architecture-models.md) | Cloud responsibility, IaC, serverless, SDN, containers, IoT, ICS/SCADA, RTOS |
| 30 | [Securing Enterprise Infrastructure](chapters/level-3-intermediate/30-securing-enterprise-infrastructure.md) | Zones, fail-open/closed, jump server, 802.1X/EAP, NGFW/UTM/WAF, IPsec, SASE |
| 31 | [Protecting Data](chapters/level-3-intermediate/31-protecting-data.md) | Encryption vs hashing vs masking vs tokenization; sovereignty; DLP |
| 32 | [Resilience & Recovery](chapters/level-3-intermediate/32-resilience-and-recovery.md) | Hot/warm/cold sites, backup types, replication ≠ backup, UPS & generators, testing |
| 33 | [Change Management, Zero Trust & Deception](chapters/level-3-intermediate/33-change-management-zero-trust-deception.md) | CAB & backout plans, gap analysis, PE/PA/PEP, honeypots & honeytokens |
| ✅ | [Level 3 Gate Test](chapters/level-3-intermediate/level-3-gate-test.md) | 90-question half-length exam: score 70% to move on |

## 🏆 Level 4 — Advanced Knowledge, 100% Exam Pass

| # | Chapter | You will learn |
|---|---|---|
| 34 | [Secure Baselines, Hardening, Wireless & Mobile](chapters/level-4-advanced/34-secure-baselines-hardening-wireless-mobile.md) | Baselines, hardening targets, heat maps, MDM, BYOD/COPE/CYOD, secure cookies, code signing |
| 35 | [Asset Management](chapters/level-4-advanced/35-asset-management.md) | Procurement → tracking → disposal; NIST 800-88; certificates of destruction |
| 36 | [Vulnerability Management](chapters/level-4-advanced/36-vulnerability-management.md) | Scans, threat feeds, CVE/CVSS, prioritization, remediation, validation |
| 37 | [Alerting & Monitoring](chapters/level-4-advanced/37-alerting-and-monitoring.md) | SIEM, SCAP, benchmarks, SNMP traps, NetFlow, alert tuning |
| 38 | [Enhancing Enterprise Capabilities](chapters/level-4-advanced/38-enhancing-enterprise-capabilities.md) | Firewall rules, IDS/IPS, web/DNS filtering, SPF/DKIM/DMARC, NAC, EDR/XDR, UBA |
| 39 | [Identity & Access Management](chapters/level-4-advanced/39-identity-and-access-management.md) | Provisioning, SAML/OAuth/OIDC/Kerberos/LDAP, access models, PAM |
| 40 | [Automation & Orchestration](chapters/level-4-advanced/40-automation-and-orchestration.md) | SOAR, playbooks, guard rails, CI/CD security, benefits vs risks |
| 41 | [Incident Response & Forensics](chapters/level-4-advanced/41-incident-response-and-forensics.md) | 7-step IR process, order of volatility, chain of custody, legal hold |
| 42 | [Investigations: Data Sources](chapters/level-4-advanced/42-investigations-data-sources.md) | Reading firewall, web, EDR, Windows/Linux, IDS, DNS logs; NetFlow vs PCAP |
| 43 | [Security Governance](chapters/level-4-advanced/43-security-governance.md) | Policies/standards/procedures, external considerations, data roles |
| 44 | [Risk Management (with the Math)](chapters/level-4-advanced/44-risk-management-math.md) | SLE/ALE/ARO, risk register & KRIs, appetite, RPO/RTO/MTBF/MTTR |
| 45 | [Third-Party Risk Management](chapters/level-4-advanced/45-third-party-risk-management.md) | Vendor assessments, SOC 2, SLA/MOU/MOA/MSA/SOW/NDA/BPA |
| 46 | [Compliance & Privacy](chapters/level-4-advanced/46-compliance-and-privacy.md) | Consequences, attestation, controller vs processor, right to be forgotten |
| 47 | [Audits, Assessments & Pen Testing](chapters/level-4-advanced/47-audits-assessments-pentesting.md) | Internal/external audits, known/partially known/unknown, passive/active recon |
| 48 | [Security Awareness](chapters/level-4-advanced/48-security-awareness.md) | Phishing campaigns, anomalous behavior, training topics, metrics |
| 49 | [Cryptography Deep Dive](chapters/level-4-advanced/49-cryptography-deep-dive.md) | AES/ChaCha20, modes, RSA/ECC/DH, PFS, HMAC, TLS 1.3, post-quantum |
| 50 | [PBQ Mastery & Memory Drills](chapters/level-4-advanced/50-pbq-mastery-and-drills.md) | 6 worked PBQs, one-page brain dump, drill tables |
| 51 | [Mock Exams & the Final Two Weeks](chapters/level-4-advanced/51-mock-exams-and-final-two-weeks.md) | Score tracking, 14-day plan, exam-day checklist |
| 📝 | [Mock Exam 1](chapters/level-4-advanced/mock-exam-1.md) · [Mock Exam 2](chapters/level-4-advanced/mock-exam-2.md) · [Mock Exam 3](chapters/level-4-advanced/mock-exam-3.md) | 3 × 90 questions, weighted like the real exam |

## How each chapter works

🎯 Goal → 🏠 Real-life story → 🖼️ Figures → 📖 Explanation → 🧠 Memory trick → ⚠️ Exam tip → 🧪 Try it → ✅ Checkpoint questions → 📌 Summary

Figures are text drawings and Mermaid diagrams, so they display directly on GitHub.
