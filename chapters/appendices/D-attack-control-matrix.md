# Appendix D — Attack ↔ Control Matrix

For every attack in this book: how to **prevent** it, how to **detect** it, and how to **respond/recover**. It's perfect for "Which control BEST…" questions and scenario PBQs.

> 💡 **How to use it:** cover the three control columns, read the attack, and say your answer out loud before checking. The **bold** control is usually the "BEST" exam answer.

---

## 🖼️ Figure D.1 — Controls Across the Attack Timeline

```
     BEFORE the attack            DURING the attack              AFTER the attack
   ────────────────────────────┬───────────────────────────────┬────────────────────────────►
   PREVENT                     │ DETECT                        │ RESPOND / RECOVER
   patching, MFA, hardening,   │ SIEM, EDR, IDS, UBA, FIM,     │ isolate, eradicate, restore
   least privilege, training,  │ logs, honeypots, DLP alerts   │ from backups, reset creds,
   encryption, segmentation    │                               │ lessons learned
```

---

## 1. Social Engineering (Ch 15, 23, 48)

| Attack | Prevent | Detect | Respond / recover |
|---|---|---|---|
| Phishing / spear phishing / whaling | **Awareness training**, email gateway, SPF/DKIM/DMARC, MFA | User reports, gateway alerts, SIEM | Purge emails, block indicators, reset credentials |
| Smishing / vishing | **Training**, call-back verification, MDM | User reports | Reset credentials, warn staff |
| Business email compromise | **Out-of-band payment verification**, two-person approval, MFA on email | Mailbox-rule monitoring, UBA, finance anomaly checks | Recall payments with the bank quickly, secure the mailbox |
| Pretexting / impersonation | **Identity-verification procedures**, training | Help-desk call logging | Review what was disclosed |
| Watering hole | **Patching** browsers/plugins, web filtering, EDR | EDR/IDS alerts, threat intel | Isolate hosts, notify the site owner |
| Typosquatting / brand impersonation | **DNS/web filtering**, register look-alike domains, training | Domain monitoring services | Takedown requests |
| Deepfake (voice/video) | **Out-of-band verification**, code words, multi-person approval | Training to recognize anomalies | Stop transactions, report |
| Tailgating / piggybacking | **Access control vestibule**, training, guards | CCTV, badge-vs-entry counts | Escort out, review footage |
| Shoulder surfing | **Privacy screens**, awareness | — | Change exposed PINs/passwords |
| Dumpster diving | **Shredding**, locked bins, clean desk policy | — | Assess what leaked |

## 2. Malware (Ch 16)

| Attack | Prevent | Detect | Respond / recover |
|---|---|---|---|
| Ransomware | **Offline/immutable backups**, EDR, patching, least privilege, segmentation, MFA | EDR behavior detection, file-change spikes, canary/honey files | Isolate, eradicate, **restore from backups**, notify as required |
| Worm | **Patching**, segmentation, host firewalls | IDS signatures, scanning spikes | Isolate segments, patch, clean |
| Virus | Anti-malware, block unknown executables/macros | Antivirus alerts | Quarantine, clean/reimage |
| Trojan / RAT | **Application allow list**, download controls, training | EDR, C2 traffic detection | Isolate, reimage, reset credentials |
| Rootkit | **Secure Boot / Measured Boot**, TPM, patching | Integrity checks, EDR, boot attestation | **Wipe and reinstall** from trusted media |
| Logic bomb | Code review, separation of duties, **change management** | FIM, code audits | Restore from backups, investigate the insider |
| Keylogger | Anti-malware, physical inspection | EDR | Reset passwords; **MFA** limits the impact |
| Spyware / bloatware / adware | Remove unneeded software, app control | AV/EDR | Uninstall, reimage |
| Fileless malware | **EDR**, PowerShell constrained mode/logging, application control | Behavior analytics, script logging | Isolate, memory capture, reimage |
| Botnet / cryptojacking | Patching, change default passwords, egress filtering | NetFlow (C2 beaconing), resource-consumption alerts | Isolate and clean bots, block C2 |

## 3. Application & Web Attacks (Ch 24, 26)

| Attack | Prevent | Detect | Respond / recover |
|---|---|---|---|
| SQL injection | **Parameterized queries**, input validation, least-privilege DB accounts, WAF | WAF/IDS alerts, `UNION SELECT`/`' OR 1=1` in logs | Block source, fix code, assess data exposure |
| XSS (stored/reflected) | **Output encoding**, input validation, CSP, HttpOnly cookies | WAF, `<script>` in logs | Remove stored payloads, invalidate sessions |
| CSRF | **Anti-CSRF tokens**, SameSite cookies, re-authentication | Unusual request patterns | Reverse unauthorized actions |
| SSRF | **URL allow lists**, block internal/metadata addresses, segmentation | Requests to 169.254.169.254 / internal IPs | Rotate exposed cloud credentials |
| Directory traversal | **Input validation**, file allow lists, least-privilege web server | `../` or `%2e%2e%2f` in logs | Fix code, check which files were read |
| Buffer overflow | **Bounds checking**, memory-safe languages, ASLR, DEP | Crashes, IDS signatures | Patch, isolate |
| Command injection | Input validation, avoid shell calls, least privilege | Unusual processes spawned by web server | Isolate, reimage |
| Privilege escalation | **Patching**, least privilege, authorization checks | New admin accounts (Event 4720/4732), EDR | Remove access, investigate |
| Race condition (TOC/TOU) | Atomic operations, proper locking | Inconsistent records | Fix code, reconcile data |
| Replay | **Nonces, timestamps**, short session lifetimes, TLS | Duplicate tokens/transactions | Invalidate sessions |
| Malicious update / supply chain | **Code-signing verification**, vendor assessment, SBOM, staged rollouts | Threat intel, EDR | Roll back, isolate, follow vendor guidance |
| Memory injection | EDR, application control, least privilege | EDR cross-process alerts | Isolate, memory forensics |

## 4. Network & Wireless Attacks (Ch 25)

| Attack | Prevent | Detect | Respond / recover |
|---|---|---|---|
| DDoS (reflected/amplified) | **DDoS mitigation service/CDN**, rate limiting, anti-spoofing, close open resolvers | Traffic spikes (NetFlow), resource exhaustion | Engage ISP/scrubbing, filter |
| SYN flood | SYN cookies, firewall/IPS limits | Many half-open connections | Rate-limit, filter |
| DNS poisoning | **DNSSEC**, patched resolvers | Unexpected DNS answers | Flush caches, fix records |
| Domain hijacking | **Registrar lock**, MFA on registrar account | Domain monitoring | Recover via registrar |
| DNS tunneling | DNS filtering, restrict outbound DNS | Long random subdomains, high TXT volume | Block domain, isolate host |
| ARP poisoning / on-path | **Encryption (TLS/VPN)**, Dynamic ARP Inspection, 802.1X | Duplicate MACs, certificate warnings | Isolate attacker port, rotate credentials |
| SSL stripping / downgrade | **HSTS**, disable old protocols, TLS 1.3 | HTTP where HTTPS expected | Fix configs, reset exposed credentials |
| Credential replay / pass-the-hash | MFA, Kerberos hardening, least privilege | Logins without password events; concurrent sessions | Reset credentials, revoke sessions |
| Rogue AP | **802.1X/NAC** on ports, wireless scans | WIDS, site surveys | Remove the device |
| Evil twin | **WPA3-Enterprise** with certificate validation, VPN | WIDS (duplicate SSIDs) | Locate and remove, reset exposed credentials |
| Deauthentication | **802.11w / WPA3** (protected management frames) | WIDS | Locate source |
| Jamming | Shielding, wired fallback | Loss of signal | Locate the source (spectrum analysis) |
| Bluesnarfing / bluejacking | Non-discoverable Bluetooth, patching, MDM | — | Disable Bluetooth, assess loss |
| Port scanning (recon) | Close unneeded ports, firewall | **Firewall/IDS logs** (many ports, one source) | Block source, watch for follow-up |

## 5. Password & Credential Attacks (Ch 17, 26)

| Attack | Prevent | Detect | Respond / recover |
|---|---|---|---|
| Brute force (online) | **Account lockout**, MFA, rate limiting | Many failures on one account (4625) | Block source, reset if succeeded |
| Brute force (offline) | **Salting + key stretching** (bcrypt/Argon2), long passwords | — (happens on attacker's machine) | Force resets after a hash leak |
| Password spraying | **MFA**, banned-password lists, smart lockout | One failure each across many accounts | Block source, reset weak passwords |
| Credential stuffing | **MFA**, unique passwords, breached-password checks | Many logins from leaked lists, high failure rates | Force resets |
| Rainbow tables | **Salting** | — | — |
| MFA fatigue | **Number matching**, limit prompts, phishing-resistant MFA | Many push requests | Reset password, investigate |
| SIM swapping | **App-based or FIDO2 MFA** instead of SMS, carrier PIN | Sudden loss of phone service | Contact carrier, secure accounts |

## 6. Cryptographic Attacks (Ch 26, 49)

| Attack | Prevent | Detect | Respond / recover |
|---|---|---|---|
| Downgrade | **Disable old protocols/ciphers**, TLS 1.3 | Scans for weak protocols | Reconfigure |
| Collision / birthday | **SHA-256 or stronger**, no MD5/SHA-1 | Crypto inventory scans | Re-issue certificates/signatures |
| Weak keys / bad randomness | Proper key lengths, CSPRNG, HSM/KMS | Crypto audits | Rotate keys |
| Key theft | **HSM/KMS**, least privilege, no hard-coded keys | Secret scanning in code repos | **Revoke and rotate** keys/certificates |

## 7. Physical Attacks (Ch 19, 26)

| Attack | Prevent | Detect | Respond / recover |
|---|---|---|---|
| Brute force (doors/locks) | Strong doors, bollards, locks | Sensors, CCTV, alarms | Guards respond, repair |
| RFID cloning | **Encrypted smart cards**, badge + PIN, RFID shielding | Impossible badge use (two places at once) | Revoke badges |
| Device theft | **Full-disk encryption**, cable locks, MDM | Asset tracking | Remote wipe, report |
| Environmental (power, HVAC, flood, fire) | UPS/generators, HVAC redundancy, fire suppression | Environmental sensors | DR plan, failover |

## 8. Insider, Cloud & Configuration Risks (Ch 14, 24, 27, 29)

| Risk | Prevent | Detect | Respond / recover |
|---|---|---|---|
| Malicious insider | **Least privilege**, separation of duties, job rotation, mandatory vacation | **UBA**, DLP, access reviews | Disable access, legal/HR process, forensics |
| Accidental insider | Training, DLP, safe defaults | DLP alerts | Contain, retrain |
| Shadow IT / shadow AI | Approved tools, policy, CASB | CASB discovery, network monitoring | Migrate data, enforce policy |
| Misconfiguration (e.g., public bucket) | **Secure baselines**, IaC with scanning, CSPM, guard rails | Configuration scans | Fix, assess exposure |
| Default credentials | **Change at install**, hardening checklists | Scans for default logins | Change immediately |
| Unpatched / EOL systems | Patch management; **isolate** what can't be patched | Vulnerability scans | Emergency patch, compensating controls |
| Zero-day | **Defense in depth**, EDR behavior detection, segmentation, least privilege | Anomaly detection, threat hunting | Contain, apply vendor mitigations |
| VM escape / resource reuse | Patch hypervisors, wipe resources | Hypervisor monitoring | Isolate host |

## 9. AI-Related Risks (Appendix A)

| Risk | Prevent | Detect | Respond / recover |
|---|---|---|---|
| Prompt injection | **Least privilege for AI**, human approval, input/output filtering | Prompt/output logging | Revoke tokens, review actions |
| Data poisoning | **Data provenance**, vetted sources | Model testing, drift monitoring | Retrain from clean data |
| Insecure output handling | **Validate/encode output** | WAF, app logs | Fix integration |
| Sensitive data leakage / shadow AI | **AI policy, approved tools, DLP** | CASB/DLP alerts | Contain, notify if required |

---

## 🧠 The 10 Controls That Appear Most Often as "BEST"

```
   1. MFA                         6. Segmentation / isolation
   2. Patching                    7. Encryption (at rest + in transit)
   3. Least privilege             8. Input validation / parameterized queries
   4. Offline/immutable backups   9. Application allow list
   5. Security awareness training 10. Monitoring (SIEM/EDR) + logging
```
