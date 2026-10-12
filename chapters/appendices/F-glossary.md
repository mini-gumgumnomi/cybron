# Appendix F — Illustrated Glossary

Plain-English definitions of the key **terms** in this book, each with a small picture-icon to help memory and the **chapter** where it's explained. (For abbreviations like SIEM or MFA, see **Appendix B**.)

> 💡 **Study tip:** read a row, cover the definition, and explain the term out loud in your own words (the Feynman technique, Chapter 11).

---

## A – B

| | Term | Definition | Ch |
|---|---|---|---|
| 🚪 | **Access control vestibule** | Two-door entry room where only one door opens at a time; stops tailgating | 19 |
| 📜 | **Acknowledgement** | A person confirming they've read and understood a policy | 46 |
| 🧠 | **Adaptive identity** | Authentication that gets stricter when risk (location, device, behavior) is higher | 33 |
| ✈️ | **Air gap** | A network physically disconnected from all others | 29 |
| 🔔 | **Alert tuning** | Adjusting detection rules to cut false positives without missing real attacks | 37 |
| ✅ | **Allow list** | Only listed items (apps, IPs) are permitted; everything else is blocked | 20, 27 |
| 📢 | **Amplified DDoS** | Small requests trigger much larger replies aimed at a victim | 25 |
| 🧭 | **Anomaly-based detection** | Flags deviations from a learned normal baseline | 20, 38 |
| 🗂️ | **Asset** | Anything valuable that needs protecting | 10 |
| 🎯 | **Attack surface** | All the points where an attacker could try to get in | 23 |
| ✍️ | **Attestation** | A formal declaration that something is true/compliant; also periodic access reviews | 39, 46, 47 |
| 🔍 | **Audit** | Formal, evidence-based check of compliance against a standard | 47 |
| 🔐 | **Authentication** | Proving who you are | 12 |
| 🎫 | **Authorization** | Deciding what you're allowed to do | 12 |
| ⚡ | **Availability** | Systems and data are there when needed | 12 |
| 🚪 | **Backdoor** | A secret way into a system that bypasses normal login | 16 |
| ↩️ | **Backout plan** | Steps to undo a change that failed | 33 |
| 💾 | **Backup** | A copy of data kept to restore after loss | 32 |
| 📏 | **Baseline (secure)** | Approved minimum security configuration for a system type | 34 |
| 📐 | **Benchmark** | Published secure-configuration guide (e.g., CIS, STIG) | 37 |
| 👆 | **Biometrics** | Authentication using body traits (fingerprint, face) | 17 |
| 🎂 | **Birthday attack** | Math shortcut that makes hash collisions easier to find | 26 |
| 🏴 | **Black hat** | Attacker who breaks in without permission | 10 |
| 📛 | **Bloatware** | Unwanted pre-installed software that adds risk | 16 |
| ⛓️ | **Blockchain** | Chain of blocks linked by hashes; tamper-evident | 28 |
| 🧱 | **Block cipher** | Encrypts fixed-size blocks of data (e.g., AES) | 49 |
| 🧲 | **Bluejacking / bluesnarfing** | Unwanted Bluetooth messages / stealing data over Bluetooth | 7 |
| 🔵 | **Blue team** | Defenders | 10, 47 |
| 🚧 | **Bollard** | Strong post that stops vehicles but lets people through | 19 |
| 🤖 | **Botnet** | Army of infected devices controlled by an attacker | 16 |
| 🔨 | **Brute force** | Trying every possible password/key until one works | 26 |
| 🥤 | **Buffer overflow** | Writing more data than a buffer holds, overwriting memory | 24 |
| 🐛 | **Bug bounty** | Paying outside researchers for reporting vulnerabilities | 36 |

## C – D

| | Term | Definition | Ch |
|---|---|---|---|
| 📜 | **Certificate (digital)** | File binding a public key to an identity, signed by a CA | 28 |
| 🧾 | **Certificate of destruction** | Proof that media was destroyed/sanitized | 35 |
| ⛓️ | **Chain of custody** | Documented record of everyone who handled evidence | 41 |
| 🔀 | **Change management** | Formal process to request, approve, test and record changes | 33 |
| 🧹 | **Clean desk policy** | No sensitive papers or notes left on desks | 19 |
| 🧼 | **Clearing / purging / destroying** | NIST 800-88 sanitization levels, from weakest to strongest | 35 |
| 🖧 | **Clustering** | Several servers acting as one, with failover | 32 |
| 🧊 | **Cold site** | Recovery site with space and power only | 32 |
| 💥 | **Collision** | Two different inputs producing the same hash | 3, 26 |
| 🧮 | **Compensating control** | Alternative control when the ideal one isn't possible | 13 |
| 📋 | **Compliance** | Meeting laws, regulations and standards, and proving it | 22, 46 |
| 🔒 | **Confidentiality** | Only authorized people can see data | 12 |
| ⚖️ | **Conflict of interest** | Personal interest that could improperly influence a decision | 45 |
| 📦 | **Container** | Lightweight app package sharing the host OS kernel | 8, 29 |
| 🚧 | **Containment** | IR step that stops an incident spreading | 41 |
| 🧑‍⚖️ | **Controller (data)** | Decides why and how personal data is processed | 43, 46 |
| 🎛️ | **Control plane** | The decision-making part (SDN, zero trust) | 29, 33 |
| 🛠️ | **Control (security)** | Anything that reduces risk | 13 |
| 🍪 | **Cookie (secure)** | Session data with Secure, HttpOnly and SameSite flags | 34 |
| 🩹 | **Corrective control** | Fixes things after an incident | 13 |
| 🔑 | **Credential stuffing** | Reusing leaked username/password pairs on other sites | 17, 26 |
| 🚨 | **Critical (data)** | Data the organization can't operate without | 21 |
| 🔢 | **Cryptographic erase** | Destroying the key to make encrypted data unreadable | 35 |
| ⛏️ | **Cryptojacking** | Malware secretly mining cryptocurrency | 16 |
| 🧑‍🔧 | **Custodian / steward (data)** | Handles day-to-day care of data | 43 |
| 🧭 | **Data owner** | Senior person accountable for a data set | 21, 43 |
| ⚙️ | **Data plane** | The part that forwards traffic / enforces decisions | 29, 33 |
| 🧑‍💼 | **Data processor** | Processes personal data on behalf of a controller | 43, 46 |
| 🌍 | **Data sovereignty** | Data is subject to the laws where it's stored | 21, 31 |
| 👤 | **Data subject** | The person the data is about | 46 |
| 📵 | **Deauthentication attack** | Forged frames kicking users off Wi-Fi | 25 |
| 🍯 | **Deception technology** | Honeypots, honeyfiles, honeytokens: decoys to catch attackers | 33 |
| 🦺 | **Decommissioning** | Securely retiring a system and its data | 27, 35 |
| 🎭 | **Deepfake** | AI-generated fake voice or video | App. A |
| 🧅 | **Defense in depth** | Multiple layers of different controls | 10, 20 |
| 🧲 | **Degaussing** | Erasing magnetic media with a strong magnetic field (not SSDs) | 35 |
| 👀 | **Detective control** | Notices or records incidents | 13 |
| 🪧 | **Deterrent control** | Discourages attackers | 13 |
| ✍️ | **Digital signature** | Hash signed with a private key: authentication, integrity, non-repudiation | 18 |
| 🧭 | **Directive control** | Tells people what to do | 13 |
| 📁 | **Directory traversal** | Using `../` to read files outside the intended folder | 26 |
| 📰 | **Disinformation** | False information spread deliberately | 15 |
| ⬇️ | **Downgrade attack** | Forcing use of an older, weaker protocol | 26 |
| 🔍 | **Due diligence / due care** | Researching risks / acting responsibly on them | 22, 45 |
| 🗑️ | **Dumpster diving** | Searching trash for useful information | 15 |

## E – H

| | Term | Definition | Ch |
|---|---|---|---|
| 🔎 | **E-discovery** | Legal process of producing electronic records | 41 |
| 🔌 | **Embedded system** | Computer built into a device for one job | 29 |
| 🔤 | **Encoding** | Reversible format change with no key (e.g., Base64): not security | 3 |
| 🔐 | **Encryption** | Turning plaintext into ciphertext with a key | 18 |
| 🧭 | **Enumeration** | Actively discovering what exists on a network | 35 |
| ⏳ | **Ephemeral credentials / keys** | Short-lived credentials or keys that expire after use | 39, 49 |
| 🧹 | **Eradication** | IR step removing the cause and attacker footholds | 41 |
| 📈 | **Escalation (automation)** | Automatically notifying higher levels about unhandled issues | 40 |
| 🎭 | **Evasion (AI)** | Modifying input so an AI model misclassifies it | App. A |
| 👯 | **Evil twin** | Fake access point copying a real network's name | 25 |
| 📄 | **Exception / exemption** | Approved temporary deviation / release from a requirement | 36, 44 |
| 🍽️ | **Expansionary / conservative / neutral** | Risk appetite types: more / less / balanced risk-taking | 44 |
| 💣 | **Exploit** | Method or code that takes advantage of a vulnerability | 10 |
| ⚠️ | **Fail-open / fail-closed** | On failure: let traffic through / block it | 30 |
| 🔁 | **Failover** | Switching to a backup system when the primary fails | 32 |
| ❎ | **False positive / negative** | Alert with no real problem / real problem with no alert | 36 |
| 🤝 | **Federation** | Trust between organizations' identity systems | 39 |
| 🧪 | **Fileless malware** | Malware living in memory and abusing built-in tools | 16 |
| 🧱 | **Firewall** | Allows or blocks traffic based on rules | 20 |
| 🔩 | **Firmware** | Software stored on a hardware chip (e.g., UEFI) | 1, 2 |
| 🔍 | **Forensics (digital)** | Legally sound evidence collection and analysis | 41 |
| 🌊 | **Fuzzing** | Feeding random/malformed input to find crashes | 36 |
| 📏 | **Gap analysis** | Comparing current state with a target to find missing controls | 33 |
| 🗺️ | **Geofencing** | Rules based on a device's location | 7, 31 |
| 🏛️ | **Governance** | How an organization is directed and controlled | 43 |
| 🔘 | **Gray hat** | Hacker without permission but "meaning well": still illegal | 10 |
| 🛤️ | **Guard rails** | Automated limits that prevent unsafe actions/configurations | 40 |
| 🤥 | **Hallucination (AI)** | AI confidently producing false information | App. A |
| 🛡️ | **Hardening** | Reducing a system's attack surface and securing its settings | 27 |
| #️⃣ | **Hashing** | One-way fixed-length fingerprint of data | 3 |
| 🗺️ | **Heat map** | Color map of Wi-Fi signal strength (or of risk) | 34, 44 |
| 📄 | **Honeyfile / honeytoken** | Decoy file / decoy credential or data | 33 |
| 🍯 | **Honeypot / honeynet** | Decoy system / decoy network | 33 |
| 🔥 | **Hot site** | Fully ready recovery site with near-live data | 32 |
| 🧑‍🤝‍🧑 | **Hybrid cloud** | Mix of private/on-premises and public cloud | 8, 29 |
| 🏢 | **Hypervisor** | Software that runs virtual machines (Type 1 / Type 2) | 8 |

## I – N

| | Term | Definition | Ch |
|---|---|---|---|
| 🪪 | **Identification** | Claiming an identity (e.g., typing a username) | 12 |
| 🪪 | **Identity proofing** | Verifying a person really is who they claim before creating an account | 39 |
| 🚩 | **Impact analysis** | Assessing what a change could affect | 33 |
| 📜 | **Implicit deny** | Anything not explicitly allowed is blocked | 20 |
| 🧭 | **Implicit trust zone** | Area behind a zero-trust PEP where some trust is assumed | 33 |
| ✈️ | **Impossible travel** | Logins from places too far apart for the time between them | 26 |
| 📈 | **Incremental / differential backup** | Changes since last backup of any kind / since last full | 32 |
| 🔎 | **Indicator** | Clue that something malicious happened | 26 |
| 💉 | **Injection** | Sending input that gets executed as commands (SQL, OS, LDAP) | 24, 26 |
| 🧑‍💼 | **Insider threat** | Threat from someone with legitimate access | 14 |
| ✅ | **Integrity** | Data is accurate and unchanged without permission | 12 |
| 🔄 | **Inventory** | Recorded list of assets | 35 |
| 🏝️ | **Isolation** | Completely cutting a system off from others | 27 |
| 🔓 | **Jailbreaking** | Removing a device's (or AI's) built-in restrictions | 7, 24, App. A |
| 🪜 | **Jump server** | Hardened host admins must pass through to reach sensitive systems | 30 |
| 🔐 | **Kerberos** | Ticket-based authentication in Windows domains | 39 |
| 🗝️ | **Key escrow** | A trusted party holds copies of keys for recovery | 28 |
| ⌨️ | **Keylogger** | Records keystrokes | 16 |
| 🏋️ | **Key stretching** | Making password hashing deliberately slow (bcrypt, PBKDF2) | 28 |
| ⛓️ | **Kill chain (Cyber)** | Seven stages of an attack, from recon to actions on objectives | 10 |
| 🧭 | **Lateral movement** | Attacker moving from one compromised system to others | 27, 47 |
| ⚖️ | **Least privilege** | Only the minimum access needed | 2, 27 |
| 🧓 | **Legacy system** | Old technology still in use, often insecure | 24 |
| 📜 | **Legal hold** | Order to preserve data for litigation | 35, 41 |
| 🎓 | **Lessons learned** | Final IR step: review and improve | 41 |
| ⚖️ | **Load balancer** | Spreads traffic across multiple servers | 30, 32 |
| 💣 | **Logic bomb** | Malicious code triggered by a date or event | 16 |
| 🗓️ | **Maintenance window** | Agreed time slot for changes | 33 |
| 🦠 | **Malware** | Malicious software | 16 |
| 🎭 | **Masking (data)** | Hiding part of data when displayed (`****4821`) | 31 |
| 💉 | **Memory injection** | Inserting code into a running process's memory | 24 |
| 🧩 | **Microservices** | App built from many small services talking via APIs | 29 |
| ⚙️ | **Misconfiguration** | Insecure settings: one of the most common vulnerabilities | 24 |
| 📰 | **Misinformation** | False information shared without intent to deceive | 15 |
| ☁️ | **Multi-cloud** | Using more than one cloud provider | 32 |
| 🌊 | **NetFlow** | Records who talked to whom, when and how much (no content) | 37 |
| ✍️ | **Non-repudiation** | Being unable to deny an action because there's proof | 12 |

## O – R

| | Term | Definition | Ch |
|---|---|---|---|
| 🌫️ | **Obfuscation** | Making data or code hard to understand | 28, 31 |
| 📋 | **Offboarding / onboarding** | Removing / granting access and equipment when people leave / join | 22, 43 |
| 🕵️ | **On-path attack** | Attacker secretly sits between two parties | 25 |
| 📚 | **Order of volatility** | Collect the most fragile evidence first (RAM before disk) | 41 |
| 🏷️ | **Passive vs active reconnaissance** | Gathering info without touching target systems vs scanning them | 47 |
| 🔑 | **Passkey** | Passwordless login using a device-held private key | 17 |
| 💧 | **Password spraying** | A few common passwords tried across many accounts | 26 |
| 🩹 | **Patch** | Vendor fix for a vulnerability | 2, 27 |
| 🥷 | **Penetration test** | Authorized simulated attack proving real impact | 47 |
| 🐷 | **Piggybacking / tailgating** | Following someone through a secure door with / without their knowledge | 19 |
| 🧭 | **Platform diversity** | Using different vendors/technologies to avoid a shared weakness | 32 |
| 📜 | **Policy / standard / procedure / guideline** | What & why / specific rules / step-by-step / optional advice | 22, 43 |
| 🏃 | **Pretexting** | Using an invented story to get information | 15 |
| 🛡️ | **Preventive control** | Stops an incident from happening | 13 |
| ⬆️ | **Privilege escalation** | Gaining more access than allowed (vertical/horizontal) | 26 |
| 💬 | **Prompt injection** | Tricking an AI into following attacker instructions | App. A |
| 🏗️ | **Provisioning / de-provisioning** | Creating / removing accounts and access | 39 |
| 🔁 | **Proxy (forward / reverse)** | Middleman for users going out / for servers receiving requests | 20, 30 |
| 🏁 | **Race condition** | Result depends on timing; attacker acts between check and use | 24 |
| 🔐 | **Ransomware** | Malware that encrypts or steals data for ransom | 16 |
| 🔴 | **Red team** | Attackers in an exercise (offensive testing) | 10, 47 |
| 🪞 | **Reflected attack** | Attack bounced off third-party servers using a spoofed IP | 25 |
| 🔁 | **Replay attack** | Capturing and resending valid authentication data | 25 |
| 🔄 | **Replication** | Continuously copying data to another place (not a backup!) | 32 |
| 📊 | **Residual / inherent risk** | Risk after / before controls | 44 |
| ⚖️ | **Risk** | Likelihood × impact of harm | 10, 44 |
| 🍽️ | **Risk appetite / tolerance** | Risk willingly pursued / acceptable variation | 44 |
| 📋 | **Risk register** | List of risks, owners, ratings and responses | 22, 44 |
| 📡 | **Rogue access point** | Unauthorized AP connected to the network | 25 |
| 🔍 | **Root cause analysis** | Finding the underlying reason for an incident | 41 |
| 🕳️ | **Rootkit** | Malware hiding deep in the OS/firmware with privileged access | 16 |
| 🌳 | **Root of trust** | Starting point all trust builds on (root CA, TPM) | 28 |

## S – Z

| | Term | Definition | Ch |
|---|---|---|---|
| 🧂 | **Salt** | Random value added to a password before hashing | 28 |
| 🏖️ | **Sandbox** | Isolated environment for running untrusted code | 34 |
| 🧼 | **Sanitization** | Removing data so it can't be recovered | 35 |
| 🏰 | **Screened subnet** | Zone between internet and internal network for public servers (old name: DMZ) | 30 |
| 🛡️ | **Secure Boot** | Firmware feature that only allows trusted, signed boot code | 2 |
| 🏰 | **Secure enclave** | Protected area inside a processor for sensitive operations | 28 |
| 🧩 | **Segmentation** | Dividing a network into zones with controlled traffic | 20, 27 |
| 🖐️ | **Separation of duties** | Splitting critical tasks between people | 22 |
| ⚡ | **Serverless** | Code runs as functions only when triggered; no servers to manage | 29 |
| 🙈 | **Shadow IT / shadow AI** | Unapproved technology / AI tools used by staff | 14, App. A |
| 🤝 | **Shared responsibility model** | Cloud provider secures the cloud; customer secures what's in it | 8, 29 |
| 👀 | **Shoulder surfing** | Watching someone enter a password or PIN | 15 |
| 🧪 | **Side-loading** | Installing apps from outside official stores | 7, 24 |
| 🔏 | **Signature-based detection** | Matching known attack patterns | 20, 38 |
| 📸 | **Snapshot** | Point-in-time copy of a system/VM | 8, 32 |
| 🎣 | **Social engineering** | Manipulating people into giving access or information | 15 |
| 🔍 | **Spear phishing / whaling** | Targeted phishing / phishing aimed at executives | 15 |
| 🖼️ | **Steganography** | Hiding data inside other data (e.g., images) | 28 |
| 🌊 | **Stream cipher** | Encrypts data as a continuous stream, a bit or byte at a time (e.g., ChaCha20) | 49 |
| 🔗 | **Supply chain attack** | Compromising a supplier to reach its customers | 23 |
| 🌐 | **Symmetric / asymmetric encryption** | One shared key / public-private key pair | 18 |
| 🗣️ | **Tabletop exercise** | Talking through a scenario around a table | 32, 41 |
| 📈 | **Technical debt** | Shortcuts that pile up and must be fixed later | 40 |
| ☠️ | **Threat** | Anything that could cause harm | 10 |
| 🦹 | **Threat actor** | The person or group behind a threat | 14 |
| 🏹 | **Threat hunting** | Proactively searching for hidden attackers | 41 |
| 🎟️ | **Tokenization** | Replacing sensitive data with a random token | 28, 31 |
| 🐴 | **Trojan** | Malware disguised as legitimate software | 16 |
| ⌨️ | **Typosquatting** | Registering misspelled domains to catch typos | 15 |
| 🧓 | **Unsupported system** | No longer receives vendor patches | 23 |
| 🧑‍🤝‍🧑 | **Version control** | Tracking every change to code/configs with rollback | 33 |
| 📦 | **Virtual machine (VM) / VM escape** | Software computer / breaking out of it to the host | 8, 24 |
| 🕳️ | **Vulnerability** | A weakness that could be exploited | 10 |
| 🔍 | **Vulnerability scan (credentialed)** | Automated check for known weaknesses (logged-in = more accurate) | 36 |
| 🌤️ | **Warm site** | Recovery site with equipment but data must be restored | 32 |
| 💧 | **Watering hole attack** | Infecting a website the targets visit | 15 |
| ⚪ | **White hat** | Ethical hacker with permission | 10 |
| 🃏 | **Wildcard certificate** | Certificate for `*.domain` (one subdomain level) | 28 |
| 🐛 | **Worm** | Self-spreading malware needing no user action | 16 |
| 🕳️ | **Zero-day** | Vulnerability exploited before a patch exists | 24 |
| 🚫 | **Zero trust** | Never trust, always verify, for every request | 33 |
