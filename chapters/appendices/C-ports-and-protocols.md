# Appendix C — Master Port & Protocol Table

Every port and protocol you're likely to meet in Security+ questions, firewall PBQs and log analysis, all in one place. The **⭐ starred** rows are the must-memorize core (also on the Chapter 50 brain-dump sheet).

> 💡 **Reminder (Chapter 5):** well-known ports are **0–1023**, registered ports **1024–49151**, dynamic/ephemeral ports **49152–65535**. A server *listens* on a fixed port; the client uses a random ephemeral port.

---

## 📖 Part 1 — The Core Table ⭐

| Port | Protocol | Transport | What it does | Secure? | Secure alternative |
|---:|---|---|---|---|---|
| ⭐ 20, 21 | FTP | TCP | File transfer (20 data, 21 control) | ❌ plaintext | SFTP (22) / FTPS (989/990) |
| ⭐ 22 | SSH / SFTP / SCP | TCP | Secure remote shell and file transfer | ✅ | — |
| ⭐ 23 | Telnet | TCP | Remote shell | ❌ plaintext | SSH (22) |
| ⭐ 25 | SMTP | TCP | Mail between servers | ❌ (unless STARTTLS) | SMTPS 465 / submission 587 with STARTTLS |
| ⭐ 49 | TACACS+ | TCP | Device administration AAA (encrypts whole payload) | ✅ | — |
| ⭐ 53 | DNS | UDP (and TCP) | Name resolution; TCP for large replies/zone transfers | ❌ | DNSSEC (integrity), DoH 443 / DoT 853 (privacy) |
| ⭐ 67, 68 | DHCP | UDP | Automatic IP configuration (67 server, 68 client) | ❌ | DHCP snooping on switches |
| ⭐ 69 | TFTP | UDP | Trivial file transfer, no authentication | ❌ | SFTP |
| ⭐ 80 | HTTP | TCP | Web | ❌ | HTTPS (443) |
| ⭐ 88 | Kerberos | TCP/UDP | Windows domain authentication tickets | ✅ | — |
| ⭐ 110 | POP3 | TCP | Download mail | ❌ | POP3S (995) |
| ⭐ 123 | NTP | UDP | Time synchronization | ❌ | NTS (Network Time Security) |
| ⭐ 143 | IMAP | TCP | Sync mail | ❌ | IMAPS (993) |
| ⭐ 161, 162 | SNMP | UDP | Device monitoring (161 polling, 162 traps) | ❌ v1/v2c | SNMPv3 |
| ⭐ 389 | LDAP | TCP/UDP | Directory queries | ❌ | LDAPS (636) |
| ⭐ 443 | HTTPS | TCP (UDP for HTTP/3) | Secure web; also SSL/TLS VPNs, DoH | ✅ | — |
| ⭐ 445 | SMB | TCP | Windows file/printer sharing | ⚠️ (SMBv1 dangerous) | SMBv3 with encryption; never expose to internet |
| ⭐ 465 | SMTPS | TCP | SMTP with implicit TLS | ✅ | — |
| ⭐ 514 | Syslog | UDP | Log forwarding | ❌ | Syslog over TLS (6514) |
| ⭐ 587 | SMTP submission | TCP | Client mail submission with STARTTLS | ✅ (with STARTTLS) | — |
| ⭐ 636 | LDAPS | TCP | LDAP over TLS | ✅ | — |
| ⭐ 993 | IMAPS | TCP | IMAP over TLS | ✅ | — |
| ⭐ 995 | POP3S | TCP | POP3 over TLS | ✅ | — |
| ⭐ 1812, 1813 | RADIUS | UDP | Authentication (1812), accounting (1813) | ⚠️ encrypts only the password | Use with EAP-TLS / RadSec |
| ⭐ 3389 | RDP | TCP (and UDP) | Windows Remote Desktop | ✅ encrypted, but a top attack target | Only via VPN/jump server + MFA |

---

## 📖 Part 2 — More Ports Worth Recognizing

### Remote Access, VPN & Tunneling

| Port | Protocol | Transport | Notes |
|---:|---|---|---|
| 500 | IKE / ISAKMP | UDP | IPsec key exchange |
| 4500 | IPsec NAT-T | UDP | IPsec through NAT |
| — | ESP / AH | IP protocols **50 / 51** | IPsec (protocol numbers, not ports!) |
| 1701 | L2TP | UDP | Usually combined with IPsec |
| 1723 | PPTP | TCP | Old, insecure VPN: avoid |
| 1194 | OpenVPN | UDP/TCP | Popular open-source VPN (TLS-based) |
| 51820 | WireGuard | UDP | Modern VPN protocol |
| 5900 | VNC | TCP | Remote desktop (cross-platform) |
| 5985, 5986 | WinRM | TCP | Windows remote management (HTTP / HTTPS) |

### Email, Web & Name Services

| Port | Protocol | Transport | Notes |
|---:|---|---|---|
| 853 | DNS over TLS (DoT) | TCP | Encrypted DNS |
| 8080 / 8443 | Alternate HTTP / HTTPS | TCP | Common for proxies, admin consoles, dev servers |
| 3268, 3269 | Global Catalog / GC over TLS | TCP | Active Directory forest-wide LDAP |
| 137–139 | NetBIOS | TCP/UDP | Old Windows networking: disable where possible |
| 135 | Microsoft RPC | TCP | Windows remote procedure calls |

### File & Storage

| Port | Protocol | Transport | Notes |
|---:|---|---|---|
| 989, 990 | FTPS | TCP | FTP over TLS (implicit mode). Explicit FTPS instead upgrades the normal port 21 connection with AUTH TLS |
| 2049 | NFS | TCP/UDP | Unix/Linux network file system |
| 3260 | iSCSI | TCP | Block storage over IP |

### Databases

| Port | Database | Notes |
|---:|---|---|
| 1433 | Microsoft SQL Server | Never expose to the internet |
| 1521 | Oracle | |
| 3306 | MySQL / MariaDB | |
| 5432 | PostgreSQL | |
| 6379 | Redis | Often left with no password: a classic misconfiguration |
| 27017 | MongoDB | Many exposed, unauthenticated databases have leaked data |

### Voice, Logging & Management

| Port | Protocol | Transport | Notes |
|---:|---|---|---|
| 5060 / 5061 | SIP / SIP over TLS | UDP/TCP | VoIP call setup |
| — | RTP / SRTP | UDP (dynamic ports) | Voice/video media (SRTP = encrypted) |
| 6514 | Syslog over TLS | TCP | Secure log forwarding |
| 179 | BGP | TCP | Internet routing between providers |

### Cloud, Containers & IoT/ICS

| Port | Protocol | Notes |
|---:|---|---|
| 2375 / 2376 | Docker API (plain / TLS) | An exposed 2375 = full control of the host |
| 6443 | Kubernetes API server | Protect with strong authentication |
| 1883 / 8883 | MQTT (plain / TLS) | IoT messaging |
| 5683 | CoAP | Lightweight IoT protocol (UDP) |
| 502 | Modbus/TCP | ICS protocol: no built-in authentication |
| 20000 | DNP3 | ICS/utility protocol |

> 🔐 Ports are **conventions**, not guarantees. Attackers can run any service on any port (e.g., a backdoor on 443 to blend in), and admins sometimes move services (SSH on 2222). Firewalls that only look at ports (Layer 4) can be fooled; **NGFWs** identify the actual application (Layer 7).

---

## 📖 Part 3 — Secure Replacement Cheat Sheet

```
   INSECURE              SECURE REPLACEMENT
   ────────────────────  ─────────────────────────────────────────────
   Telnet 23         →   SSH 22
   HTTP 80           →   HTTPS 443 (+ HSTS)
   FTP 20/21         →   SFTP 22  or  FTPS 989/990
   TFTP 69           →   SFTP 22
   POP3 110          →   POP3S 995
   IMAP 143          →   IMAPS 993
   SMTP 25           →   SMTPS 465 / submission 587 + STARTTLS
   LDAP 389          →   LDAPS 636
   SNMPv1/v2c 161    →   SNMPv3
   Syslog 514        →   Syslog over TLS 6514
   DNS 53            →   DNSSEC (integrity) / DoT 853 / DoH 443 (privacy)
   SIP 5060 + RTP    →   SIP-TLS 5061 + SRTP
   PPTP 1723         →   IPsec (IKEv2) / WireGuard / TLS VPN
   SMBv1             →   SMBv3 (encryption on), never exposed to the internet
   SSL / TLS 1.0-1.1 →   TLS 1.2 / TLS 1.3
```

---

## 📖 Part 4 — Port Drills 🏋️

### Drill 1 — Fill in the port (answers below)
1. SSH  2. RDP  3. LDAPS  4. DNS  5. SNMP traps  6. Kerberos  7. IMAPS  8. SMB  9. Syslog  10. TACACS+

### Drill 2 — Name the protocol
1. 443  2. 23  3. 1812  4. 995  5. 123  6. 69  7. 636  8. 3306  9. 500 (UDP)  10. 587

### Drill 3 — Firewall thinking
A server must provide **secure web**, **secure remote admin from 10.0.9.0/24 only**, and **secure LDAP queries** to internal clients. Which inbound ports should be allowed, and from where?

<details>
<summary><b>Show answers</b></summary>

**Drill 1:** 1 → 22 · 2 → 3389 · 3 → 636 · 4 → 53 · 5 → 162 · 6 → 88 · 7 → 993 · 8 → 445 · 9 → 514 · 10 → 49

**Drill 2:** 1 → HTTPS · 2 → Telnet · 3 → RADIUS authentication · 4 → POP3S · 5 → NTP · 6 → TFTP · 7 → LDAPS · 8 → MySQL · 9 → IKE (IPsec) · 10 → SMTP submission

**Drill 3:** **TCP 443** from any (secure web) · **TCP 22** from **10.0.9.0/24 only** (SSH admin) · **TCP 636** from the **internal client subnets** (LDAPS) · everything else **denied** (implicit deny).

</details>
