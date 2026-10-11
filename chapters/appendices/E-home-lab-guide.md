# Appendix E — Home Lab Guide

A safe, free home lab turns reading into **doing**, which is exactly what PBQs test. This appendix shows you how to build one step by step, keep it **safe and legal**, and which **exercises** to run for each part of the book.

---

## ⚖️ Rule Zero: Safety and Legality

```
   ┌───────────────────────────────────────────────────────────────────────────┐
   │ 1. Only scan, attack or test systems you OWN or have WRITTEN permission   │
   │    to test. Practise sites that explicitly allow testing are fine.        │
   │ 2. Keep vulnerable and attacker VMs on HOST-ONLY or INTERNAL networks,    │
   │    never bridged to your home network, never exposed to the internet.     │
   │ 3. Never run real malware outside an isolated, snapshotted VM, and as a   │
   │    beginner, avoid live malware altogether.                               │
   │ 4. Take a SNAPSHOT before every exercise so you can undo mistakes.        │
   │ 5. Don't reuse real passwords in the lab.                                 │
   └───────────────────────────────────────────────────────────────────────────┘
```

---

## 📖 Part 1 — What You Need 🧰

| Item | Minimum | Comfortable |
|---|---|---|
| CPU | 4 cores with virtualization (Intel VT-x / AMD-V) enabled in UEFI | 6–8 cores |
| RAM | 8 GB (run 2 small VMs at a time) | 16–32 GB |
| Disk | 100 GB free (SSD strongly recommended) | 250 GB+ SSD |
| Hypervisor | **VirtualBox** (free) | VirtualBox, VMware Workstation Pro (free for personal use), Hyper-V, or Proxmox on a spare PC |
| Internet | Only to download images and updates | — |

> 💡 **No powerful PC?** Use free **cloud labs** (Part 5), or rent a small cloud VM for a few hours (remember to delete it).

---

## 📖 Part 2 — The Lab Network 🗺️

## 🖼️ Figure E.1 — Recommended Starter Lab

```
                          🌍 Internet (updates only)
                                   │
                         ┌─────────┴──────────┐
                         │  VirtualBox NAT    │  (VMs reach the internet;
                         │  network           │   nothing reaches them)
                         └─────────┬──────────┘
                                   │
                       ┌───────────┴────────────┐
                       │  pfSense / OPNsense    │  WAN = NAT
                       │  firewall VM           │  LAN = internal network "labnet"
                       └───────────┬────────────┘
                                   │  internal network "labnet" (isolated)
          ┌──────────────┬─────────┴─────┬──────────────────┬──────────────────┐
          │              │               │                  │                  │
   ┌──────┴──────┐ ┌─────┴───────┐ ┌─────┴───────┐  ┌───────┴───────┐  ┌───────┴───────┐
   │ Kali Linux  │ │ Ubuntu      │ │ Windows     │  │ Metasploitable│  │ Wazuh or      │
   │ (attacker / │ │ Server      │ │ (evaluation)│  │ 2 / DVWA      │  │ Security Onion│
   │ tester)     │ │ (target,    │ │ + optional  │  │ (deliberately │  │ (SIEM /       │
   │             │ │ hardening)  │ │ AD server   │  │ vulnerable)   │  │ monitoring)   │
   └─────────────┘ └─────────────┘ └─────────────┘  └───────────────┘  └───────────────┘
```

Start small: **Kali + one target** is enough for most exercises. Add the firewall and SIEM later.

### VirtualBox Network Modes (from Chapter 9)

| Mode | Use it for |
|---|---|
| **NAT** | VMs that need internet for updates (nothing outside can reach them) |
| **Host-only** | Lab VMs that only need to talk to each other and your PC |
| **Internal network** | Fully isolated lab traffic (safest for attack practice) |
| **Bridged** | ⚠️ Avoid for lab targets: the VM appears on your real home network |

---

## 📖 Part 3 — Building It Step by Step 🛠️

1. **Enable virtualization** in your PC's UEFI/BIOS (Intel VT-x or AMD-V).
2. **Install VirtualBox** from virtualbox.org.
3. **Create an internal network** named `labnet` (VM settings → Network → Attached to: *Internal Network*).
4. **Download images only from official sources**, and **verify their hashes** (Chapter 3):
   - **Kali Linux** (kali.org): ready-made VirtualBox images
   - **Ubuntu Server** (ubuntu.com)
   - **Windows** evaluation editions (Microsoft Evaluation Center)
   - **Metasploitable 2** (Rapid7) or **DVWA** (Damn Vulnerable Web Application): deliberately vulnerable targets, **internal network only**
   - Optional: **pfSense** or **OPNsense** (firewall), **Wazuh** or **Security Onion** (SIEM/IDS)
5. **Create the VMs** (2 CPUs, 2–4 GB RAM each to start) and attach them to `labnet`.
6. **Take a "clean" snapshot** of every VM.
7. **Write down IP addresses** (`ip a` / `ipconfig`) and test with `ping`.

```bash
# Verify a download before using it (Linux/macOS; compare with the official hash)
sha256sum kali-linux-*.7z
```

---

## 📖 Part 4 — Lab Exercises Mapped to the Book 🧪

| # | Exercise | Skills | Chapters |
|---|---|---|---|
| 1 | Find IP/MAC/gateway on each VM; draw your lab network | Networking basics | 4, 9 |
| 2 | Capture a TCP handshake and a DNS lookup in **Wireshark** | OSI, TCP, DNS | 5, 6 |
| 3 | Log into an FTP or Telnet service on Metasploitable and capture the **plaintext password** | Insecure protocols | 6, 9, 42 |
| 4 | **Nmap** scan the target: `nmap -sV <ip>`; list open ports and versions | Recon, attack surface | 9, 23, 47 |
| 5 | **Harden** the Ubuntu server: patch, enable `ufw`, disable unneeded services, change defaults; scan again and compare | Hardening | 27, 34 |
| 6 | Create users and groups; set file permissions with `chmod`; test least privilege | Access control | 2, 39 |
| 7 | Hash files, encrypt/decrypt with OpenSSL, create a key pair, CSR and self-signed certificate | Crypto, PKI | 3, 18, 28 |
| 8 | Practise **SQL injection and XSS** on DVWA (low security level), then raise the level and see the defenses | Web attacks | 24, 26 |
| 9 | Brute-force SSH on your own Ubuntu VM with a tiny wordlist, then find the **failed logins** in `/var/log/auth.log`; add fail2ban/lockout and retry | Password attacks, logs | 26, 42 |
| 10 | Send all VM logs to **Wazuh**; create an alert for 5 failed logins in 2 minutes | SIEM, alerting | 37 |
| 11 | Configure **pfSense** rules: allow HTTPS to the web server, SSH only from Kali, deny all else; test with Nmap | Firewall rules (PBQ!) | 20, 38, 50 |
| 12 | Snapshot, "break" the server (delete files), then **restore**: practise backup/recovery | Resilience | 32 |
| 13 | **Forensic acquisition**: image a small virtual disk with `dd`, hash before/after, fill in a chain-of-custody form | Forensics | 41 |
| 14 | Plant a **honeyfile** (e.g., a free Canarytoken) and trigger it | Deception | 33 |
| 15 | Write and run a small **automation script** (create a user, log it, then disable it) | Automation | 40 |
| 16 | Windows evaluation VM: explore **Event Viewer**, find 4624/4625, configure an account lockout policy | Windows logs, policy | 9, 38, 42 |

---

## 📖 Part 5 — Free Online Labs (no installation) 🌐

| Platform | Good for |
|---|---|
| **TryHackMe** | Beginner-friendly guided rooms (networking, Linux, web, SOC); has a Security+-style learning path |
| **PortSwigger Web Security Academy** | Free, high-quality web vulnerability labs (SQLi, XSS, CSRF, SSRF, traversal) |
| **Hack The Box Academy** | Structured modules; harder machines later |
| **OverTheWire (Bandit)** | Learning the Linux command line through a game |
| **Blue Team Labs Online / CyberDefenders** | Defensive challenges: log and PCAP analysis |
| **malware-traffic-analysis.net** | PCAP exercises (open only in an isolated VM) |
| **Gandalf (Lakera)** | Prompt-injection practice (Appendix A) |
| **CTF competitions** (e.g., picoCTF) | Fun, varied challenges for beginners |

---

## 📖 Part 6 — Lab Hygiene Checklist ✅

```
   ☐ Virtualization enabled; hypervisor installed
   ☐ Images downloaded from official sites and hashes verified
   ☐ Vulnerable VMs on INTERNAL/HOST-ONLY networks only
   ☐ Clean snapshot taken for every VM
   ☐ Lab passwords are unique (never your real ones)
   ☐ Lab notebook: IPs, credentials, what you did, what you learned
   ☐ VMs shut down when not in use (and cloud VMs deleted)
```

> 📓 **Keep a lab notebook.** For each exercise write: goal → commands → what happened → what it taught you → which exam objective it relates to. It becomes your best revision resource.
