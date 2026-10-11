# 🧱 Level 1 Gate Test

**50 questions · Chapters 1–10 · Target: 40 / 50 (80%) to move on to Level 2**

Set a timer for **50 minutes** (about 1 minute per question, the same pace as the real exam). Write your answers down, then check them with the answer key at the bottom. For every wrong answer, re-read the chapter shown in the key and add the question to your **mistake journal** (Chapter 11).

---

## Section A — Computers & Operating Systems (Ch 1–2)

**1.** Which component holds data only while the computer is powered on?
A. SSD  B. HDD  C. RAM  D. UEFI

**2.** Which chip on the motherboard securely stores encryption keys and supports Measured Boot?
A. CPU  B. NIC  C. TPM  D. GPU

**3.** What is the first software that runs when a computer is switched on?
A. The kernel  B. UEFI/BIOS firmware  C. The bootloader  D. The login screen

**4.** A user receives a file named `payslip.pdf.exe`. What type of file is it?
A. A PDF document  B. A compressed archive  C. An executable program  D. A text file

**5.** Which principle says users should only have the access they need to do their job?
A. Defense in depth  B. Availability  C. Non-repudiation  D. Least privilege

**6.** On Linux, a file has permissions `-rwxr-----`. What can members of the file's group do?
A. Read, write and execute  B. Read only  C. Nothing  D. Execute only

**7.** What do we call a running instance of a program in memory?
A. A process  B. A service  C. A driver  D. A file system

**8.** A vendor no longer releases security patches for an operating system. This is called:
A. Zero-day  B. Sandboxing  C. Side-loading  D. End-of-life

**9.** Which UEFI feature prevents unsigned bootloaders from running?
A. Secure Boot  B. UAC  C. sudo  D. NTFS

---

## Section B — Data Representation (Ch 3)

**10.** What is binary `11000000` in decimal?
A. 128  B. 172  C. 192  D. 255

**11.** How many bits does one hexadecimal digit represent?
A. 2  B. 4  C. 8  D. 16

**12.** Which transformation is designed to be one-way?
A. SHA-256 hashing  B. AES encryption  C. Base64 encoding  D. Compression

**13.** A developer stores passwords as Base64 strings. What is the main problem?
A. Base64 can be reversed by anyone without a key  B. Base64 is too slow  C. Base64 produces collisions  D. Base64 requires a certificate

**14.** Which security goal does hashing mainly support?
A. Confidentiality  B. Integrity  C. Availability  D. Authorization

**15.** Two different files produce the same hash value. What is this called?
A. An overflow  B. A salt  C. A collision  D. A replay

**16.** Adding one more bit to an encryption key's length does what to the number of possible keys?
A. Adds one more key  B. Nothing  C. Squares it  D. Doubles it

---

## Section C — Networking (Ch 4–5)

**17.** Which address is 48 bits long and identifies a network card?
A. IPv4  B. MAC  C. IPv6  D. Port

**18.** Which of these is a **private** IPv4 address?
A. 8.8.8.8  B. 192.168.10.20  C. 172.32.1.5  D. 203.0.113.9

**19.** A PC has the address `169.254.33.7`. What does this MOST likely mean?
A. It is using IPv6  B. It could not reach a DHCP server  C. It is a web server  D. It is behind NAT

**20.** Which device forwards traffic **between different networks** using IP addresses?
A. Router  B. Switch  C. Hub  D. Access point

**21.** Which device sends every frame out of **every** port, making eavesdropping easy?
A. Switch  B. Hub  C. Router  D. Firewall

**22.** What does NAT allow?
A. Automatic patching  B. Encryption of all traffic  C. Faster Wi-Fi  D. Many private devices to share one public IP

**23.** Which protocol maps an IP address to a MAC address on a local network?
A. DNS  B. ARP  C. DHCP  D. NTP

**24.** At which OSI layer do routers mainly operate?
A. Layer 2  B. Layer 3  C. Layer 4  D. Layer 7

**25.** What is the correct order of the TCP three-way handshake?
A. ACK, SYN, SYN-ACK  B. SYN, ACK, FIN  C. SYN, SYN-ACK, ACK  D. SYN, RST, ACK

**26.** Which transport protocol is connectionless and used for most DNS queries?
A. TCP  B. ARP  C. ICMP  D. UDP

**27.** What range are the well-known ports?
A. 0–1023  B. 1024–49151  C. 49152–65535  D. 0–65535

**28.** An attacker sends thousands of SYN packets but never completes the handshake. What is this?
A. ARP poisoning  B. Evil twin  C. SYN flood  D. Port mirroring

---

## Section D — Protocols & Ports (Ch 6)

**29.** Which port does HTTPS use by default?
A. 80  B. 22  C. 3389  D. 443

**30.** What is the secure replacement for Telnet?
A. HTTP  B. FTP  C. SNMPv2  D. SSH

**31.** Which port is used by RDP?
A. 445  B. 1433  C. 3389  D. 53

**32.** Which protocol automatically gives devices an IP address, mask, gateway and DNS server?
A. DHCP  B. DNS  C. LDAP  D. SMTP

**33.** Which DNS record type stores SPF information used to fight email spoofing?
A. TXT  B. MX  C. A  D. PTR

**34.** Which protocol and port provide **secure** directory lookups?
A. LDAPS 636  B. LDAP 389  C. Kerberos 88  D. SNMP 161

**35.** SFTP runs over which protocol?
A. TLS  B. SSH  C. HTTP  D. Telnet

**36.** Which version of SNMP adds authentication and encryption?
A. SNMPv1  B. SNMPv2c  C. SNMPv3  D. None of them

**37.** Why is accurate time (NTP) important for security?
A. It lets logs from different systems be correlated  B. It speeds up encryption  C. It blocks malware  D. It assigns IP addresses

---

## Section E — Wireless, Mobile & Cloud (Ch 7–8)

**38.** Which Wi-Fi security protocol is the strongest?
A. WEP  B. WPA  C. WPA2  D. WPA3

**39.** An attacker sets up an access point with the same SSID as the company's network. What is this?
A. Rogue AP  B. Evil twin  C. Bluesnarfing  D. Jamming

**40.** Which feature should be disabled on a Wi-Fi router because its PIN can be brute-forced?
A. SSID broadcast  B. DHCP  C. WPS  D. WPA3

**41.** In enterprise Wi-Fi, which server checks each user's credentials?
A. DNS  B. DHCP  C. NTP  D. RADIUS

**42.** Stealing contacts and photos from a phone over Bluetooth is called:
A. Bluejacking  B. Skimming  C. Bluesnarfing  D. Jailbreaking

**43.** Installing an app from a website instead of the official app store is called:
A. Rooting  B. Geofencing  C. Tethering  D. Side-loading

**44.** Which hypervisor type runs directly on the hardware?
A. Type 1  B. Type 2  C. Container engine  D. Emulator

**45.** In a SaaS model, who is responsible for managing user access and protecting the company's data?
A. Only the cloud provider  B. The customer  C. Nobody  D. The internet provider

---

## Section F — Command Line & Security Basics (Ch 9–10)

**46.** Which command shows open ports and active network connections on Windows?
A. `netstat -ano`  B. `tracert`  C. `ping`  D. `nslookup`

**47.** You see `USER bob` and `PASS Winter2025` in a packet capture. What does this indicate?
A. Strong encryption is in use  B. The traffic is hashed  C. A VPN is active  D. An insecure plaintext protocol is in use

**48.** An unpatched web server is an example of a:
A. Threat  B. Threat actor  C. Control  D. Vulnerability

**49.** Ransomware that makes hospital systems unusable mainly attacks which part of the CIA triad?
A. Confidentiality  B. Integrity  C. Availability  D. Non-repudiation

**50.** In the Cyber Kill Chain, malware contacting an attacker's server for instructions is called:
A. Command and Control  B. Weaponization  C. Delivery  D. Reconnaissance

---

## ✅ Answer Key

<details>
<summary><b>Click to show answers (try first!)</b></summary>

| # | Ans | Why (chapter) |
|---|---|---|
| 1 | C | RAM is volatile (Ch 1) |
| 2 | C | TPM stores keys and supports Measured Boot (Ch 1, 2) |
| 3 | B | Firmware runs first, then the bootloader, then the kernel (Ch 2) |
| 4 | C | The last extension (`.exe`) is the real one (Ch 2) |
| 5 | D | Least privilege (Ch 2) |
| 6 | B | Group = `r--`, read only (Ch 2) |
| 7 | A | A process is a running program (Ch 2) |
| 8 | D | End-of-life / unsupported (Ch 2) |
| 9 | A | Secure Boot (Ch 2) |
| 10 | C | 128 + 64 = 192 (Ch 3) |
| 11 | B | 1 hex digit = 4 bits (Ch 3) |
| 12 | A | Hashing is one-way (Ch 3) |
| 13 | A | Encoding is reversible by anyone (Ch 3) |
| 14 | B | Integrity (Ch 3) |
| 15 | C | Collision (Ch 3) |
| 16 | D | Each extra bit doubles the keyspace (Ch 3) |
| 17 | B | MAC = 48 bits (Ch 4) |
| 18 | B | 192.168.0.0/16 is private. 172.32.x is outside 172.16–31 (Ch 4) |
| 19 | B | APIPA (169.254.x.x) means DHCP failed (Ch 4) |
| 20 | A | Router (Ch 4) |
| 21 | B | Hub (Ch 4) |
| 22 | D | NAT shares one public IP (Ch 4) |
| 23 | B | ARP (Ch 4) |
| 24 | B | Layer 3, Network (Ch 5) |
| 25 | C | SYN, SYN-ACK, ACK (Ch 5) |
| 26 | D | UDP (Ch 5) |
| 27 | A | 0–1023 (Ch 5) |
| 28 | C | SYN flood (Ch 5) |
| 29 | D | 443 (Ch 6) |
| 30 | D | SSH (Ch 6) |
| 31 | C | 3389 (Ch 6) |
| 32 | A | DHCP (Ch 6) |
| 33 | A | TXT (Ch 6) |
| 34 | A | LDAPS 636 (Ch 6) |
| 35 | B | SSH (Ch 6) |
| 36 | C | SNMPv3 (Ch 6) |
| 37 | A | Log correlation and timelines (Ch 6) |
| 38 | D | WPA3 (Ch 7) |
| 39 | B | Evil twin (Ch 7) |
| 40 | C | WPS (Ch 7) |
| 41 | D | RADIUS (Ch 7) |
| 42 | C | Bluesnarfing (Ch 7) |
| 43 | D | Side-loading (Ch 7) |
| 44 | A | Type 1 / bare metal (Ch 8) |
| 45 | B | The customer: data and access are always the customer's job (Ch 8) |
| 46 | A | `netstat -ano` (Ch 9) |
| 47 | D | Plaintext credentials mean an insecure protocol (e.g., FTP) (Ch 9) |
| 48 | D | Vulnerability (Ch 10) |
| 49 | C | Availability (Ch 10) |
| 50 | A | Command and Control (C2) (Ch 10) |

**Scoring:**
- **45–50:** 🏆 Excellent. Go straight to Level 2.
- **40–44:** ✅ Pass. Review the chapters you missed, then start Level 2.
- **30–39:** 🔁 Re-study the weakest section (A–F) and retake the test in 3–4 days.
- **Below 30:** 📖 Re-read Chapters 4–6 (networking is the biggest foundation), redo the "Try It" labs, and retake in a week.

</details>
