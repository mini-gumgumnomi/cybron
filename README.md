# Cybron — *From Zero to Security+*

A beginner-first, figure-heavy book for passing the **CompTIA Security+ (SY0-701)** exam. It starts from "what is a computer?" and finishes at full exam readiness. AI/LLM security is covered in Appendix A, which gives you a head start on the AI content expected in the coming **SY0-801** version (always check CompTIA's official SY0-801 objectives once they are published).

## The four levels

| Level | Name | Chapters | Status |
|---|---|---|---|
| 🧱 1 | Basic Foundation to Understand to Start | 1–11 + Gate Test | ✅ Written |
| 🌱 2 | Beginner for Exam | 12–22 + Gate Test | ✅ Written |
| 📈 3 | Can Score ~40% in Exam | 23–33 + Gate Test | ✅ Written |
| 🏆 4 | Advanced Knowledge — 100% Exam Pass | 34–51 + 3 Mock Exams | ✅ Written |
| 📎 | Appendices | A–G | ✅ Written |

📘 **[Full Book Plan](BOOK_PLAN.md)**: every chapter, topic, figure, study schedule, and a map from each exam objective to its chapter.

## 🧭 How to use this book

**1. Read the levels in order.** Each level builds on the one before. Read one chapter at a time, top to bottom: story → figure → explanation → memory trick → exam tip → try it → checkpoint questions (answers are hidden under "Show answers"; try first, then check).
- *Already have A+ or Network+ knowledge?* Skim Level 1, but still take the **Level 1 Gate Test**. If you score 80%+, go straight to Level 2.

**2. Plan about 4–5 months from zero** at 1–1.5 hours a day (Level 1: 3–4 weeks · Level 2: 3 weeks · Level 3: 4–5 weeks · Level 4: 5–6 weeks). A simple daily routine: 10 min flashcard review → 40 min reading (redraw the figure from memory) → 15 min "Try it" lab → 10 min checkpoint questions, writing every wrong answer in a mistake journal. See section 8 of the [Book Plan](BOOK_PLAN.md) for a week-by-week schedule.

**3. Use the gate tests as checkpoints.** At the end of each level, take its gate test without notes. Move on only at the target score (**80%** for Level 1, **75%** for Level 2, **70%** for Level 3). If you miss it, re-read the chapters behind the questions you got wrong and retake the test a few days later.

**4. Save the mock exams for the end.** Don't take the mock exams early: they are your final dress rehearsal. Finish Chapters 34–50 first, then follow the **14-day plan in Chapter 51**: Mock 1 on day 1, Mock 2 on day 7, Mock 3 on day 12, each timed (90 minutes) and followed by a careful mistake review. **Book the real exam when you score 85%+ on two different mocks with no domain below 75%.**

**5. Use the appendices alongside the chapters, not after them.**

| Appendix | When to use it |
|---|---|
| B (Acronyms) and F (Glossary) | From Level 2 onward: turn the terms you miss into daily flashcards |
| C (Ports) | Start memorizing the ⭐ ports after Chapter 6; drill them weekly until exam day |
| D (Attack ↔ Control) | From Level 3 onward, for "Which control is BEST?" questions |
| E (Home Lab) | Set up the lab after Chapter 9 and do each exercise when you reach its chapter |
| G (Question Bank) | Whenever a gate test or mock shows a weak exam objective: it lists every question for that objective, plus 84 bonus questions |
| A (AI & LLM Security) | Not needed for SY0-701. Read it after Level 4 if you are taking SY0-801 or want the background |

**6. Practise performance-based questions (PBQs).** The real exam mixes multiple-choice questions with hands-on PBQs. The mock exams are multiple-choice only, so do the PBQs in **Chapter 50** and the labs in **Appendix E** as well.

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
| ✅ | [Level 3 Gate Test](chapters/level-3-intermediate/level-3-gate-test.md) | 90-question practice exam on Domains 1–3: score 70% to move on |

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

## 📎 Appendices

| | Appendix | What's inside |
|---|---|---|
| A | [AI & LLM Security (SY0-801 ready)](chapters/appendices/A-ai-and-llm-security.md) | How LLMs work, prompt injection, poisoning, model theft, hallucinations, shadow AI, AI controls & frameworks, 10 practice questions |
| B | [Acronym Dictionary](chapters/appendices/B-acronym-dictionary.md) | About 380 acronyms in plain English, with the chapter that teaches each |
| C | [Master Port & Protocol Table](chapters/appendices/C-ports-and-protocols.md) | Must-know ports, extra ports, secure replacements, port drills |
| D | [Attack ↔ Control Matrix](chapters/appendices/D-attack-control-matrix.md) | Prevent / detect / respond controls for every major attack family |
| E | [Home Lab Guide](chapters/appendices/E-home-lab-guide.md) | Safe lab setup, network diagram, 16 exercises mapped to chapters, free online labs |
| F | [Illustrated Glossary](chapters/appendices/F-glossary.md) | About 220 key terms with picture-icons and chapter references |
| G | [Practice Question Bank](chapters/appendices/G-practice-question-bank.md) | Every question in the book indexed by exam objective, plus 84 bonus questions |

## How each chapter works

🎯 Goal → 🏠 Real-life story → 🖼️ Figures → 📖 Explanation → 🧠 Memory trick → ⚠️ Exam tip → 🧪 Try it → ✅ Checkpoint questions (open recall + 6 exam-style multiple-choice) → 📌 Summary

Figures are text drawings and Mermaid diagrams, so they display directly on GitHub.
