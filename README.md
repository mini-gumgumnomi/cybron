# Cybron — *From Zero to Security+*

A beginner-first, figure-heavy book for passing the **CompTIA Security+ (SY0-701)** exam. It starts from "what is a computer?" and finishes at full exam readiness. AI/LLM security is covered in an appendix, so the book is also ready for the coming **SY0-801** update.

## The four levels

| Level | Name | Chapters | Status |
|---|---|---|---|
| 🧱 1 | Basic Foundation to Understand to Start | 1–11 + Gate Test | ✅ Written |
| 🌱 2 | Beginner for Exam | 12–22 + Gate Test | ✅ Written |
| 📈 3 | Can Score ~40% in Exam | 23–33 + Gate Test | ✅ Written |
| 🏆 4 | Advanced Knowledge — 100% Exam Pass | 34–51 | ⏳ Planned |

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

## How each chapter works

🎯 Goal → 🏠 Real-life story → 🖼️ Figures → 📖 Explanation → 🧠 Memory trick → ⚠️ Exam tip → 🧪 Try it → ✅ Checkpoint questions → 📌 Summary

Figures are text drawings and Mermaid diagrams, so they display directly on GitHub.
