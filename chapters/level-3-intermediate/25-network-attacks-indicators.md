# Chapter 25 — Network Attacks & Their Indicators

**Level 3 · Can Score ~40%** · *Exam objective 2.4 (network attacks)*

---

## 🎯 Goal

By the end of this chapter you will recognize the network attacks named in Security+: **DDoS** (including **amplified** and **reflected**), **DNS attacks**, **wireless attacks**, **on-path** attacks, **credential replay** and **malicious code**. For each one you'll know **what it looks like** (indicators) and **how to stop it**.

---

## 🏠 Real-Life Story: Three Ways to Ruin a Pizza Shop 🍕

1. **Flood it:** a prankster gets 10,000 people to phone the shop at once. Real customers can't get through. → **Denial of service**
2. **Swap the address:** someone changes the shop's listing in the phone book, so customers call a fake shop instead. → **DNS attack**
3. **Intercept the orders:** someone stands between the customer and the shop, reading (and changing) every order passing through. → **On-path attack**

---

## 📖 Part 1 — Denial of Service (DoS) and DDoS 🌊

- **DoS (Denial of Service):** an attack that makes a system **unavailable** (harms **availability**).
- **DDoS (Distributed DoS):** the attack comes from **many machines at once**, usually a **botnet** (Chapter 16), which makes it much bigger and harder to block (you can't just block one IP address).

### Types of DoS by What They Exhaust

| Type | What it uses up | Example |
|---|---|---|
| **Volumetric** | **Bandwidth** (the internet pipe) | Huge floods of UDP traffic |
| **Protocol** | **Connection tables** in servers/firewalls | **SYN flood** (Chapter 5): half-open connections |
| **Application-layer (Layer 7)** | **Server resources** (CPU, database) | Thousands of "search" requests per second |

### Reflected DDoS 🪞

The attacker **sends requests to innocent third-party servers** with a **spoofed (faked) source IP**: the **victim's** IP. The servers **reply to the victim**, which gets flooded by traffic it never asked for. The attack is "reflected" off the servers, hiding the attacker.

### Amplified DDoS 📢

A reflected attack where each **small request triggers a much larger reply**. The attacker gets **more attack traffic than they send**.

## 🖼️ Figure 25.1 — Reflection + Amplification

```
   ATTACKER                     OPEN SERVERS (innocent)                VICTIM
   (sends small requests,       DNS / NTP / memcached                  203.0.113.5
    FAKES the source IP
    as the victim's)

   🦹 ── 60-byte request ─────►  📡 DNS server  ── 3,000-byte reply ───►  🎯
      "from: 203.0.113.5"       📡 NTP server   ── huge reply ────────►  🎯  💥 overwhelmed
                                📡 memcached    ── enormous reply ────►  🎯
   Small input in ──────────────────────────────── MUCH bigger output to the victim

   Reported amplification factors (US-CERT): DNS ~28-54x, NTP up to ~556x,
   memcached up to ~51,000x
```

> 💡 **Reflected** = bounced off third parties using a **spoofed source IP**. **Amplified** = the bounced reply is **much bigger** than the request. Most big DDoS attacks are **both**.

### Indicators of DDoS
- Sudden, massive spike in traffic; website slow or unreachable (**resource inaccessibility**)
- Huge numbers of connections from many IPs or countries
- High CPU, memory or bandwidth use (**resource consumption**)
- Floods of DNS/NTP **responses** you never requested (reflection)

### Defenses
- **DDoS protection / scrubbing services** (cloud providers absorb and filter the flood), **CDNs**
- **Rate limiting**, firewalls, IPS, load balancers
- **Anti-spoofing filters** at ISPs (stop packets with fake source IPs)
- **Close open resolvers**, i.e., don't run DNS/NTP/memcached servers that answer anyone on the internet

---

## 📖 Part 2 — DNS Attacks 📒

DNS translates names to IP addresses (Chapter 6). If attackers corrupt that, they control **where you go**.

| Attack | What happens | Defense |
|---|---|---|
| **DNS poisoning / cache poisoning** | Fake records are inserted into a DNS server's **cache**, so users asking for `bank.com` get the **attacker's IP** | **DNSSEC** (signed DNS answers), patched DNS servers |
| **DNS spoofing (local)** | Changing a victim's **hosts file** or local DNS settings to point names at the attacker | Endpoint protection, file integrity monitoring |
| **Domain hijacking** | Attacker takes over the **domain registration** (e.g., phishes the registrar account) and changes where the domain points | MFA and **registrar lock** on the domain account |
| **DNS tunneling** | Hiding data or commands **inside DNS queries** to **sneak data out** or talk to C2 through firewalls that allow DNS | DNS monitoring, DNS filtering, look for unusually long/random subdomains |
| **DNS amplification** | DDoS using open DNS resolvers (see Part 1) | Close open resolvers, rate limiting |

## 🖼️ Figure 25.2 — DNS Cache Poisoning

```
   NORMAL:   💻 "Where is bank.com?" ──► 📒 DNS cache: bank.com = 198.51.100.10 ──► 🏦 real bank

   POISONED: 🦹 injects a fake record into the cache:  bank.com = 203.0.113.66
             💻 "Where is bank.com?" ──► 📒 DNS cache: bank.com = 203.0.113.66 ──► 🎭 fake bank site
                                                                                    (steals logins)
   The user typed the RIGHT address and still ended up on the WRONG site.
```

> 🔍 **DNS tunneling clue:** queries like `aGVsbG8gd29ybGQ.x7k2.evil-example.net`: long, random-looking subdomains, very frequent, often to one strange domain. That's data being smuggled out in **Base64** (Chapter 3).

---

## 📖 Part 3 — Wireless Attacks 📶

| Attack | What happens | Indicator / Defense |
|---|---|---|
| **Rogue access point** | An **unauthorized AP** connected to the company network (by an attacker, or by an employee for convenience: shadow IT) | Wireless scans / **WIDS** spot unknown APs; **802.1X** on switch ports |
| **Evil twin** | A fake AP with the **same SSID** as a real one, often with a stronger signal | Users see two identical network names; use **WPA3-Enterprise** with certificate checks and VPN |
| **Deauthentication attack** | Forged "disconnect" frames kick users off Wi-Fi, often to push them onto an evil twin or to capture the reconnection handshake | Sudden mass disconnections; **802.11w / Protected Management Frames** (mandatory in WPA3) |
| **Jamming** | Radio noise blocks the frequency (a wireless DoS) | No connection at all; locate the source |
| **WPS / PSK cracking** | Capturing the WPA2 handshake and guessing the passphrase offline, or brute-forcing the WPS PIN | **Long passphrases**, disable WPS, use WPA3 |
| **Bluetooth attacks** | Bluejacking, bluesnarfing (Chapter 7) | Non-discoverable, patched devices |
| **RFID/NFC attacks** | Skimming or cloning badges (Chapter 26) | Encrypted cards, shielding |

## 🖼️ Figure 25.3 — Deauth + Evil Twin Combo

```
   1. 🦹 sends forged "deauth" frames ──► 💻 victim gets disconnected from real "CorpWiFi"
   2. 🦹 runs a fake AP also named "CorpWiFi" with a STRONGER signal
   3. 💻 automatically reconnects to the strongest "CorpWiFi" = the attacker's
   4. 🦹 now sits ON-PATH: sees traffic, serves fake login pages
```

---

## 📖 Part 4 — On-Path Attacks (Man-in-the-Middle) 🕵️

An **on-path attack** (formerly "man-in-the-middle," MITM) puts the attacker **between two communicating parties**, where they can **read, capture or modify** traffic while both sides think they're talking directly.

## 🖼️ Figure 25.4 — Alice, Bob and Mallory

```
   EXPECTED:    👩 Alice ◄──────────────────────────────────────► 👨 Bob

   ON-PATH:     👩 Alice ◄────► 🦹 Mallory (attacker) ◄────► 👨 Bob
                              reads 👀  changes ✏️  replays 🔁
```

**How attackers get on-path:**
- **ARP poisoning** (Chapter 4): telling the LAN "I am the gateway."
- **Evil twin / rogue AP** (above).
- **DNS poisoning** (above).
- **Rogue DHCP server** handing out the attacker as the gateway (Chapter 6).
- **Malicious proxy** settings or a compromised router.
- **On-path browser** (also called man-in-the-browser): malware inside the browser modifies pages and transactions.

**Indicators:**
- Certificate warnings ("Your connection is not private") on sites that normally work
- **Duplicate MAC addresses** in ARP tables (two IPs, one MAC)
- HTTPS sites suddenly loading as HTTP (**SSL stripping** / downgrade)
- Unexpected gateway or DNS server addresses

**Defenses:** **encryption everywhere** (TLS, VPN, SSH), **HSTS** (forces browsers to use HTTPS), certificate validation, **Dynamic ARP Inspection** and **DHCP snooping** on switches, **802.1X**, WPA3.

### SSL Stripping (Downgrade Example)

```
   👩 browser ── http://bank.com ──► 🦹 ── https://bank.com ──► 🏦
            ◄── plain HTTP page ────     ◄── encrypted page ────
   The attacker talks HTTPS to the bank but plain HTTP to the victim,
   so the victim's password crosses the attacker's machine unencrypted.
   Defense: HSTS (the browser refuses to use plain HTTP for that site).
```

---

## 📖 Part 5 — Credential Replay 🔁

The attacker **captures valid authentication data** (a password hash, session token, Kerberos ticket, or cookie) and **sends it again** ("replays" it) to log in as the victim, **without knowing the actual password**.

## 🖼️ Figure 25.5 — Replay

```
   1. 👩 logs in ──► session token "abc123" ──► 🖥️ server       (attacker captures "abc123")
   2. 🦹 later sends "abc123" ─────────────────► 🖥️ server       "Welcome back, Alice!" 😱
```

- Related: **pass-the-hash** (reusing a Windows password hash), **session hijacking**, **cookie theft**.
- **Defenses:** encrypt traffic (so tokens can't be sniffed), **timestamps and nonces** (one-time random values) so old messages are rejected, **short session lifetimes**, **MFA**, Kerberos (built-in timestamps).
- **Indicators:** the same session used from two locations (**concurrent session usage**), logins without a matching password-entry event.

---

## 📖 Part 6 — Malicious Code on the Network 🦠

Network-delivered malicious code: **worms** spreading through vulnerable services, **exploit kits** on websites, malicious scripts in web traffic, **C2 beaconing** (malware "phoning home" at regular intervals).

**Indicators:**
- Many hosts suddenly scanning port 445 (worm behavior)
- Regular, small outbound connections to an unknown IP every N seconds (**beaconing**)
- Traffic to known-bad IPs/domains (from **threat intelligence feeds**)
- Unusual protocols on unusual ports

**Defenses:** IPS signatures, network segmentation, egress (outbound) filtering, DNS filtering, EDR, patching.

---

## 🖼️ Figure 25.6 — Network Attack Cheat Sheet ⭐

| Attack | Key clue in a question | Best defense |
|---|---|---|
| DDoS | Massive traffic from many sources; site down | DDoS mitigation service, rate limiting |
| Reflected | Responses come from legit servers; **spoofed source IP** | Anti-spoofing, close open resolvers |
| Amplified | Small requests → huge responses (DNS/NTP/memcached) | Same + rate limiting |
| DNS poisoning | Correct URL typed, wrong IP / fake site | **DNSSEC** |
| DNS tunneling | Long random subdomains, high DNS volume to one domain | DNS monitoring/filtering |
| Rogue AP | Unknown AP on the corporate network | WIDS, 802.1X |
| Evil twin | Two networks with the same SSID | WPA3-Enterprise, VPN |
| Deauthentication | Mass Wi-Fi disconnects | 802.11w / WPA3 |
| On-path (ARP poisoning) | Duplicate MACs, cert warnings | Encryption, DAI, 802.1X |
| SSL stripping | HTTPS site shows as HTTP | **HSTS** |
| Credential replay | Reused token/hash, no password typed | Nonces/timestamps, encryption, MFA |
| Malicious code / C2 | Beaconing, worm scanning | IPS, egress filtering, EDR |

---

## 🧠 Memory Tricks

- **DoS = one attacker. DDoS = Distributed (a botnet army).**
- **Reflected = bounced off innocent servers. Amplified = bounced AND made bigger.**
- **On-path = "Mallory in the middle."**
- **Evil twin = same name, fake network. Rogue AP = unauthorized network on the inside.**
- **Replay = "record and play back the key."**
- **DNSSEC = DNS + SECurity signatures** → stops poisoning.
- **HSTS = "HTTPS Strictly, To Sites"** → stops SSL stripping.

---

## ⚠️ Exam Tip

- *"Attackers send small queries to open DNS resolvers with the victim's IP as the source."* → **Reflected + amplified DDoS** (DNS amplification).
- *"Users typing the correct URL are sent to a fraudulent site."* → **DNS poisoning.** Fix: **DNSSEC.**
- *"An ARP table shows the gateway's IP mapped to a workstation's MAC."* → **ARP poisoning / on-path.**
- *"An attacker captures a session token and reuses it later."* → **Replay** (credential replay / session hijacking).
- *"Two access points broadcast the same SSID; one belongs to an attacker."* → **Evil twin.**
- *"An employee plugged a personal wireless router into the office network."* → **Rogue access point.**
- *"Large numbers of DNS queries with random-looking subdomains to one external domain."* → **DNS tunneling** (data exfiltration).

---

## 🧪 Try It (20 minutes)

1. **See your ARP table** (`arp -a`). Note your gateway's MAC. If you ever see the same MAC listed for two different IPs, that's a red flag.
2. **Check DNSSEC:** on Linux/macOS run `dig +dnssec cloudflare.com`. Look for `RRSIG` records: those are DNS signatures.
3. **See HSTS:** in your browser's developer tools (F12 → Network), click a request to a big site (e.g., google.com) and find the `strict-transport-security` response header.
4. **Watch a DDoS map:** search "live DDoS attack map" (e.g., from a security vendor) to see attacks happening worldwide.

---

## ✅ Checkpoint Questions

1. What's the difference between DoS and DDoS?
2. Explain reflected vs amplified DDoS.
3. Which three protocols are commonly abused for amplification?
4. A user types the correct URL but reaches a fake site. What attack is MOST likely, and what's the defense?
5. What are the signs of DNS tunneling?
6. What's the difference between a rogue AP and an evil twin?
7. Name three ways an attacker can get "on-path."
8. What is SSL stripping, and what stops it?
9. What is credential replay, and how do nonces/timestamps help?
10. What is C2 beaconing?

<details>
<summary><b>Show answers</b></summary>

1. **DoS** comes from a single source. **DDoS** comes from **many distributed sources** (often a botnet).
2. **Reflected:** requests with a **spoofed source IP** (the victim's) are sent to third-party servers, which **reply to the victim**. **Amplified:** those replies are **much larger** than the requests.
3. **DNS, NTP, memcached** (also others such as SSDP and CLDAP).
4. **DNS poisoning** (or spoofing). Defense: **DNSSEC** (plus patched, well-configured DNS servers).
5. **Unusually long or random subdomains**, a **high volume of DNS queries** to one domain, large TXT records, DNS traffic at odd times.
6. A **rogue AP** is an **unauthorized** AP connected to the company network. An **evil twin** **impersonates** a legitimate network by copying its **SSID**.
7. E.g., **ARP poisoning, evil twin/rogue AP, DNS poisoning, rogue DHCP server**, malicious proxy, compromised router.
8. An on-path attacker **downgrades HTTPS to HTTP** for the victim while using HTTPS to the server. **HSTS** stops it.
9. **Capturing and reusing** valid authentication data (tokens, hashes, tickets). **Nonces/timestamps** make each message unique and time-limited, so replayed copies are rejected.
10. Malware **regularly contacting** its command-and-control server (e.g., every 60 seconds) to receive instructions.

</details>

---

## 📌 Chapter Summary

| Family | Attacks | Signature defenses |
|---|---|---|
| DoS/DDoS | Volumetric, protocol (SYN flood), application; **reflected**, **amplified** | Scrubbing/CDN, rate limiting, anti-spoofing |
| DNS | Poisoning, hijacking, tunneling, amplification | **DNSSEC**, registrar lock, DNS monitoring |
| Wireless | Rogue AP, evil twin, deauth, jamming, PSK/WPS cracking | WPA3-Enterprise, WIDS, 802.11w |
| On-path | ARP poisoning, SSL stripping, rogue DHCP | Encryption, **HSTS**, DAI, DHCP snooping |
| Replay | Token/hash/ticket reuse | Nonces, timestamps, MFA |
| Malicious code | Worms, C2 beaconing | IPS, egress filtering, EDR |

**Next chapter →** *Chapter 26: Application, Password, Crypto & Physical Attacks + Indicators of Compromise.* The rest of objective 2.4, plus the classic warning signs every analyst must recognize.
