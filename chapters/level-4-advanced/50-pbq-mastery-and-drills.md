# Chapter 50 — PBQ Mastery & Memory Drills

**Level 4 · Advanced Knowledge** · *Exam skills for all domains*

---

## 🎯 Goal

By the end of this chapter you will:
- recognize the common **performance-based question (PBQ)** types and have a method for each,
- have worked through **six full practice PBQs** with solutions,
- own a **one-page brain-dump sheet** you can rewrite from memory in under 5 minutes,
- and have **drill tables** (ports, acronyms, process orders, attack ↔ control) for daily practice.

---

## 🏠 Real-Life Story: The Driving Test 🚗

The written driving theory test asks, *"What does this sign mean?"* The practical test puts you **in the car**: you must actually **check mirrors, signal, and park**. You can know every rule and still stall if you've never practised.

**PBQs are the practical driving test of Security+.** You'll drag, drop, configure and analyze. The only way to get good is to **practise the movements**.

---

## 📖 Part 1 — PBQ Survival Strategy 🧭

```
   1. At the start, LOOK at each PBQ for ~30 seconds. Short and clear? Do it now.
      Long or confusing? FLAG it and move on.
   2. Answer all multiple-choice questions first (≈ 45–50 s each).
   3. Return to flagged PBQs with the time you saved (aim to leave 20–25 min).
   4. Read EVERY instruction line: "select ALL that apply," "each item may be used once,"
      "drag the BEST control."
   5. Partial credit is possible, so never leave a PBQ blank. Fill in what you're sure of first.
   6. Scroll! Some PBQs have hidden tabs, extra log lines or extra devices.
```

## 🖼️ Figure 50.1 — Common PBQ Types

| Type | What you do | Chapters |
|---|---|---|
| **Matching / drag-and-drop** | Match attacks to descriptions, controls to types, ports to protocols | 13, 15, 16, 6 |
| **Firewall / ACL configuration** | Fill in or fix rules (source, destination, port, action) | 20, 27, 38 |
| **Network placement** | Drag devices (WAF, IDS, load balancer, jump server) onto a diagram | 30 |
| **Log analysis** | Read logs, identify the attack, the source and the fix | 26, 42 |
| **Process ordering** | Put IR steps, order of volatility or change-management steps in order | 41, 33 |
| **Configuration choices** | Choose Wi-Fi settings, certificate types, MFA methods, backup types | 34, 28, 17, 32 |
| **Scenario → control** | Pick the best mitigation for each scenario | 27, 38 |

---

## 📖 Part 2 — Six Practice PBQs (with Solutions) ✍️

### PBQ 1 — Match the Attack 🧩

Drag each description to the correct attack: **Smishing · Whaling · Watering hole · Typosquatting · Pretexting · BEC · Vishing**

| # | Description |
|---|---|
| a | A fake "parcel delivery fee" text message with a link |
| b | Attackers compromise a forum popular with the target company's engineers |
| c | The CFO receives a carefully personalized email about an acquisition |
| d | `micros0ft-login.com` hosts a fake login page |
| e | A caller claims to be from the bank's fraud team and asks for a one-time code |
| f | A caller invents a story about being a new auditor needing staff lists |
| g | An attacker uses the CEO's real, compromised mailbox to request an urgent wire transfer |

<details><summary><b>Solution</b></summary>

a → **Smishing** · b → **Watering hole** · c → **Whaling** · d → **Typosquatting** · e → **Vishing** · f → **Pretexting** · g → **BEC**

</details>

---

### PBQ 2 — Fix the Firewall 🧱

A web server (**10.1.1.10**, in the screened subnet) must accept **HTTPS from anywhere**. It must reach the database (**10.2.2.20**) on **TCP 3306**. Admins (**10.9.9.0/24**) need **SSH** to the web server. **Everything else must be blocked.** Here is the current rule set. Find and fix the **three** problems.

```
   #  Action  Source         Destination   Port      Proto
   1  DENY    any            any           any       any
   2  ALLOW   any            10.1.1.10     443       TCP
   3  ALLOW   any            10.1.1.10     23        TCP
   4  ALLOW   10.1.1.10      10.2.2.20     3306      TCP
   5  ALLOW   any            10.1.1.10     22        TCP
```

<details><summary><b>Solution</b></summary>

1. **Rule 1 (deny any/any) is at the TOP**, so it blocks everything and no ALLOW rule is ever reached. **Move it to the bottom**, as the final "deny everything else" rule (firewalls read rules top-down and stop at the first match).
2. **Rule 3 allows Telnet (23) from anywhere**: plaintext and not required. **Delete it.**
3. **Rule 5 allows SSH from `any`**, but only the admin subnet should have it. Change the source to **10.9.9.0/24** (least privilege).

The corrected rule set:

```
   1  ALLOW   any            10.1.1.10     443   TCP   (HTTPS)
   2  ALLOW   10.1.1.10      10.2.2.20     3306  TCP   (web → DB only)
   3  ALLOW   10.9.9.0/24    10.1.1.10     22    TCP   (admin SSH only)
   4  DENY    any            any           any   any   (deny all else, log)
```

</details>

---

### PBQ 3 — Place the Devices 🗺️

Place each device in the best location: **WAF · IDS sensor · Load balancer · Jump server · VPN concentrator · Forward proxy**

```
   Internet ── [ Edge firewall ] ──┬── SCREENED SUBNET: [ ? A ] → [ ? B ] → web servers 1-3
                                   │                    [ ? C ] (remote staff connect here)
                                   └── [ Internal firewall ] ──┬── STAFF LAN: users browse via [ ? D ]
                                                               ├── SERVER ZONE: admins enter via [ ? E ]
                                                               └── SPAN port copying LAN traffic → [ ? F ]
```

<details><summary><b>Solution</b></summary>

A → **Load balancer** (spreads traffic across web servers 1–3) · B → **WAF** (inspects web traffic right in front of the web servers; A and B can also be swapped, since many designs put the WAF first) · C → **VPN concentrator** · D → **Forward proxy** · E → **Jump server** · F → **IDS sensor** (passive, on a SPAN port).

</details>

---

### PBQ 4 — Read the Logs 📜

```
   [Web server access log]
   10:41:02 203.0.113.77 "GET /download.php?file=report.pdf"              200
   10:41:09 203.0.113.77 "GET /download.php?file=../../../../etc/passwd"   200
   10:41:15 203.0.113.77 "GET /download.php?file=../../../../etc/shadow"   403
   [Windows Security log, HR-PC-07]
   11:02:10 4625 user=jsmith src=198.51.100.5 (x 37 in 2 min)
   11:02:55 4625 user=akhan  src=198.51.100.5
   11:02:56 4625 user=lpatel src=198.51.100.5
   11:02:57 4625 user=mrossi src=198.51.100.5 ... (1 attempt each for 240 users)
```

Questions: (1) What attack happened at 10:41 and was it successful? (2) What two attacks appear at 11:02? (3) Give one fix for each.

<details><summary><b>Solution</b></summary>

1. **Directory traversal.** It **succeeded** for `/etc/passwd` (HTTP **200**) but was blocked for `/etc/shadow` (403). Fix: **input validation / allow-list filenames**, run the web server with least privilege, add a WAF rule.
2. **Brute force** against `jsmith` (37 failures on one account) and **password spraying** (one attempt each across 240 accounts) from the same IP.
3. Fixes: **account lockout + MFA** (brute force); **MFA, banned-password lists, monitoring/blocking the source IP, smart lockout** (spraying).

</details>

---

### PBQ 5 — Put It in Order 🔢

**(a) Incident response:** Recovery · Detection · Lessons learned · Containment · Preparation · Eradication · Analysis
**(b) Order of volatility (most volatile first):** Disk image · Backup tapes · RAM · CPU cache · Remote syslog data
**(c) Change management:** Implement · Request · Approval (CAB) · Document · Impact analysis · Test

<details><summary><b>Solution</b></summary>

(a) **Preparation → Detection → Analysis → Containment → Eradication → Recovery → Lessons learned**
(b) **CPU cache → RAM → Disk image → Remote syslog data → Backup tapes**
(c) **Request → Impact analysis → Test → Approval (CAB) → Implement → Document**

</details>

---

### PBQ 6 — Configure It Right ⚙️

Choose the BEST option for each requirement:

| # | Requirement | Options |
|---|---|---|
| 1 | Corporate Wi-Fi where each employee logs in with their own credentials | WPA2-PSK · WPA3-Enterprise · WEP · Open + captive portal |
| 2 | One certificate for `www.`, `mail.` and `shop.example.com` | Self-signed · Wildcard `*.example.com` · Code-signing · Root CA |
| 3 | Phishing-resistant MFA for administrators | SMS code · Email code · FIDO2 security key · Security questions |
| 4 | Restore with only the last full backup + one other set | Incremental · Differential · Snapshot only · Replication |
| 5 | Stop emails spoofing your domain from being delivered | SPF only · DKIM only · DMARC with p=reject (plus SPF & DKIM) · TLS |
| 6 | Allow only approved applications on kiosks | Block list · Application allow list · Antivirus · DLP |

<details><summary><b>Solution</b></summary>

1. **WPA3-Enterprise** (802.1X/RADIUS) · 2. **Wildcard** · 3. **FIDO2 security key** · 4. **Differential** · 5. **DMARC p=reject with SPF and DKIM** · 6. **Application allow list**

</details>

---

## 📖 Part 3 — The One-Page Brain Dump 🧠📄

Practise **rewriting this whole page from memory** in under 5 minutes, every day in your final two weeks. (Follow your test center's rules about when you may write on the provided whiteboard/notes.)

## 🖼️ Figure 50.2 — Brain-Dump Sheet

```
 ┌──────────────────────────────────────────────────────────────────────────────────┐
 │ PORTS  20/21 FTP · 22 SSH/SFTP · 23 Telnet · 25 SMTP · 53 DNS · 67/68 DHCP ·     │
 │ 69 TFTP · 80 HTTP · 88 Kerberos · 110 POP3 · 123 NTP · 143 IMAP · 161/162 SNMP · │
 │ 389 LDAP · 443 HTTPS · 445 SMB · 465/587 SMTPS · 514 Syslog · 636 LDAPS ·        │
 │ 993 IMAPS · 995 POP3S · 1812/1813 RADIUS · 3389 RDP · 49 TACACS+                 │
 ├──────────────────────────────────────────────────────────────────────────────────┤
 │ CONTROLS  Categories: Technical · Managerial · Operational · Physical            │
 │ Types: Preventive · Deterrent · Detective · Corrective · Compensating · Directive│
 ├──────────────────────────────────────────────────────────────────────────────────┤
 │ IR  Prep → Detect → Analyze → Contain → Eradicate → Recover → Lessons            │
 │ VOLATILITY  registers/cache → RAM → swap/temp → disk → remote logs → config →    │
 │ archives                                                                         │
 ├──────────────────────────────────────────────────────────────────────────────────┤
 │ RISK  SLE = AV x EF · ALE = SLE x ARO · ARO(once per N yrs) = 1/N                │
 │ RPO = data loss · RTO = downtime · MTBF = between failures · MTTR = to repair    │
 │ Responses: Mitigate · Transfer · Avoid · Accept (exception/exemption)            │
 ├──────────────────────────────────────────────────────────────────────────────────┤
 │ CRYPTO  Encrypt with THEIR public · Sign with YOUR private                       │
 │ Symmetric: AES (ChaCha20) · Asymmetric: RSA, ECC, DH · Hash: SHA-256             │
 │ Avoid:  DES, 3DES, RC4, MD5, SHA-1, ECB · Salt=rainbow · Stretch=brute force     │
 │ CRL=list · OCSP=live check · Wildcard=*.domain · CSR has PUBLIC key              │
 ├──────────────────────────────────────────────────────────────────────────────────┤
 │ ZERO TRUST  PE decides · PA arranges · PEP enforces (control vs data plane)      │
 │ 802.1X  supplicant → authenticator (switch/AP) → auth server (RADIUS)            │
 │ EMAIL  SPF=servers · DKIM=signature · DMARC=policy+reports                       │
 │ ACCESS  MAC=labels · DAC=owner · RBAC=role · Rule=rules · ABAC=attributes        │
 │ SITES  Hot=ready · Warm=needs data · Cold=empty                                  │
 │ BACKUP  Incremental=since last any · Differential=since last full                │
 │ CVSS  Low 0.1-3.9 · Med 4-6.9 · High 7-8.9 · Critical 9-10                       │
 │ AGREEMENTS  SLA levels · MOU intent · MOA formal · MSA umbrella · SOW project ·  │
 │ NDA secret · BPA partners                                                        │
 └──────────────────────────────────────────────────────────────────────────────────┘
```

---

## 📖 Part 4 — Drill Tables 🏋️

### Drill A — Attack ↔ Best Control

| Attack | Best control(s) |
|---|---|
| SQL injection | Parameterized queries, input validation, WAF |
| XSS | Output encoding, input validation, CSP, HttpOnly cookies |
| CSRF | Anti-CSRF tokens, SameSite cookies |
| Directory traversal | Input validation, file allow lists, least privilege |
| Buffer overflow | Bounds checking, memory-safe languages, ASLR, DEP |
| Brute force | Account lockout, MFA, rate limiting |
| Password spraying | MFA, banned-password lists, monitoring across accounts |
| Rainbow tables | Salting (+ key stretching) |
| Phishing | Training, email filtering, SPF/DKIM/DMARC, MFA |
| Ransomware | Offline/immutable backups, EDR, patching, segmentation, least privilege |
| DDoS | DDoS mitigation service/CDN, rate limiting, anti-spoofing |
| DNS poisoning | DNSSEC |
| ARP poisoning / on-path | Encryption (TLS/VPN), Dynamic ARP Inspection, 802.1X |
| SSL stripping | HSTS |
| Evil twin / rogue AP | WPA3-Enterprise, WIDS, 802.1X |
| Replay | Nonces, timestamps, session expiry |
| Tailgating | Access control vestibule, training |
| Default credentials | Change at install, hardening |
| Zero-day | Defense in depth, EDR/behavior detection, segmentation |
| Insider data theft | Least privilege, DLP, UBA, separation of duties |
| Supply chain | Vendor assessments, SBOM, code signing verification |

### Drill B — Acronym Sprint (cover the right column and test yourself)

| Acronym | Meaning | Acronym | Meaning |
|---|---|---|---|
| AAA | Authentication, Authorization, Accounting | MDM | Mobile Device Management |
| ABAC | Attribute-Based Access Control | MFA | Multifactor Authentication |
| ALE / ARO / SLE | Annualized Loss Expectancy / Annualized Rate of Occurrence / Single Loss Expectancy | MOU / MOA | Memorandum of Understanding / Agreement |
| APT | Advanced Persistent Threat | MTBF / MTTR | Mean Time Between Failures / To Repair |
| BEC | Business Email Compromise | NAC | Network Access Control |
| BIA | Business Impact Analysis | NGFW | Next-Generation Firewall |
| BYOD / COPE / CYOD | Bring / Corporate-Owned Personally Enabled / Choose Your Own Device | OCSP | Online Certificate Status Protocol |
| CASB | Cloud Access Security Broker | OSINT | Open-Source Intelligence |
| CRL / CSR | Certificate Revocation List / Signing Request | PAM | Privileged Access Management |
| CVE / CVSS | Common Vulnerabilities and Exposures / Scoring System | PKI | Public Key Infrastructure |
| DLP | Data Loss Prevention | RPO / RTO | Recovery Point / Time Objective |
| DMARC / DKIM / SPF | Email authentication trio | SASE | Secure Access Service Edge |
| EDR / XDR | Endpoint / Extended Detection & Response | SCAP | Security Content Automation Protocol |
| FIM | File Integrity Monitoring | SIEM | Security Information & Event Management |
| HSM / TPM | Hardware Security Module / Trusted Platform Module | SOAR | Security Orchestration, Automation & Response |
| IaC | Infrastructure as Code | SSO | Single Sign-On |
| ICS / SCADA | Industrial Control Systems / Supervisory Control and Data Acquisition | UBA | User Behavior Analytics |
| IdP / SP | Identity Provider / Service Provider | WAF | Web Application Firewall |
| KRI | Key Risk Indicator | ZTNA | Zero Trust Network Access |

> The **official CompTIA acronym list** (at the end of the exam objectives PDF) has 300+ entries. Turn it into flashcards.

### Drill C — Daily 10-Minute Routine (final 2 weeks)

```
   Minute 0-5   Rewrite the brain-dump sheet from memory; check it; fix gaps in red
   Minute 5-8   20 port/acronym flashcards (Anki)
   Minute 8-10  2 PBQ-style items: one ordering drill + one attack→control match
```

---

## 🧠 Memory Tricks

- **PBQ rule: "Flag, finish, return."**
- **Firewall PBQs: look for (1) deny-all at the top, (2) insecure protocols, (3) "any" where a specific source belongs.**
- **Log PBQs: find WHO (source IP/user), WHAT (attack pattern), DID IT WORK (status code / 4624 after 4625s), and the FIX.**
- **Placement PBQs: WAF and load balancer in front of web servers; IDS on a SPAN/tap; jump server at the entrance to the admin zone; VPN concentrator at the edge.**

---

## ⚠️ Exam Tip

- PBQs can show **more information than you need**. Don't get distracted by extra devices or log lines.
- In "drag the BEST control" PBQs, each control may be usable **once** or **multiple times**. Read the instructions.
- If a PBQ freezes or behaves oddly, tell the proctor. Don't spend time fighting the interface.
- Partial credit means **every correct drag counts**. Do the sure ones first.

---

## 🧪 Try It (40 minutes)

1. **Redo all six PBQs** above **without** looking at the solutions, timing yourself (target: 4 minutes each).
2. **Rewrite the brain-dump sheet** from memory. Circle anything you missed and make flashcards for it.
3. **Create your own PBQ:** draw a small network with 4 zones, then write a firewall rule set for it. Swap with a study partner and fix each other's rules.

---

## ✅ Checkpoint Questions

1. What's the recommended order for tackling PBQs and multiple-choice questions?
2. In a firewall PBQ, what's the most common ordering mistake?
3. Where should an IDS sensor be placed so it never blocks traffic?
4. In a log, what shows that a brute-force attack succeeded?
5. What HTTP status code shows that a directory traversal attempt succeeded?
6. Which backup type needs only the last full plus one more set to restore?
7. Which email-security record actually tells receivers to reject spoofed mail?
8. What's the difference between brute force and spraying in a log?
9. Why should you never leave a PBQ blank?
10. What should go on your brain-dump sheet?

<details>
<summary><b>Show answers</b></summary>

1. **Glance at PBQs, flag the long ones, do all multiple-choice, then return** to the flagged PBQs.
2. A **deny-all (or broad deny) rule placed above specific allow rules**, so they're never reached (or an allow-any at the top).
3. On a **SPAN/mirror port or network tap** (passive, out of band).
4. Many **failed logons (4625)** followed by a **successful logon (4624)** for the same account/source.
5. **200 (OK)** for the traversal path (e.g., `../../etc/passwd`).
6. **Differential.**
7. **DMARC** (with `p=reject`).
8. **Brute force:** many failures on **one** account. **Spraying:** one or a few failures across **many** accounts.
9. **Partial credit** is possible, and there's no penalty for wrong answers.
10. **Ports, control categories/types, IR steps, order of volatility, risk formulas and RPO/RTO/MTBF/MTTR, crypto key rules, zero trust/802.1X/email trios, access models, site/backup types, CVSS bands, agreement types.**

</details>

---

## 📌 Chapter Summary

| Skill | Key points |
|---|---|
| PBQ strategy | Glance → flag → MCQs → return; read every instruction; partial credit |
| PBQ types | Matching, firewall rules, placement, log analysis, ordering, configuration, scenario → control |
| Practice | 6 worked PBQs: redo them timed |
| Brain dump | One page from memory, daily, in under 5 minutes |
| Drills | Attack ↔ control, acronyms, 10-minute daily routine |

**Next chapter →** *Chapter 51: Full Mock Exams & the Final Two Weeks.* Three full-length practice exams, a 14-day plan, and your exam-day checklist.
