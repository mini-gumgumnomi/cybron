# Chapter 7 — Wireless & Mobile Basics

**Level 1 · Basic Foundation to Understand to Start**

---

## 🎯 Goal

By the end of this chapter you will understand how **Wi-Fi, Bluetooth, NFC, RFID and cellular** networks work, how Wi-Fi security evolved from **WEP to WPA3**, and why phones and tablets are some of the hardest devices to secure.

---

## 🏠 Real-Life Story: Talking in a Crowded Room 🗣️

A wired network is like two people passing **notes through a private tube**. Only someone who cuts into the tube can read them.

A wireless network is like two people **talking out loud in a crowded room**. Radio waves go in **every direction**, through walls, into the car park and the building next door. **Anyone nearby can listen.** That's why wireless security is all about two things:

1. **Encryption:** speaking in a secret language, so listeners hear only gibberish.
2. **Authentication:** making sure the person you're talking to is who they say they are.

```
        🏢 Office                         🚗 Parking lot
   ┌────────────────────┐
   │   ACCESS POINT     │ )))   )))   )))   )))   👂 Attacker with a laptop
   │   laptops, phones  │                         can still "hear" the signal
   └────────────────────┘
        Wi-Fi does not stop at the wall!
```

---

## 📖 Wi-Fi Basics

**Wi-Fi** is the brand name for wireless LAN technology based on the **IEEE 802.11** standards.

| Term | Meaning | Analogy |
|---|---|---|
| **Access Point (AP)** | The device that broadcasts Wi-Fi and connects wireless devices to the wired network | A radio tower for your building |
| **SSID** | The network's **name** ("CoffeeShop_Guest") | The sign on a shop door |
| **BSSID** | The **MAC address** of a specific AP | The shop's exact street address |
| **Channel** | The specific radio frequency "lane" in use | A lane on a motorway |
| **Band** | The frequency range: **2.4 GHz, 5 GHz, 6 GHz** | Which motorway |

## 🖼️ Figure 7.1 — The Three Wi-Fi Bands

```
   Band       Range        Speed        Crowding           Notes
   ───────    ─────────    ─────────    ───────────────    ─────────────────────────────
   2.4 GHz    🟢 Longest    🔴 Slowest    🔴 Very crowded     Only 3 non-overlapping
                                                            channels: 1, 6, 11.
                                                            Microwaves & Bluetooth too.
   5 GHz      🟡 Medium     🟢 Fast       🟢 Less crowded     Many channels
   6 GHz      🔴 Shortest   🟢 Fastest    🟢 Very clear       Wi-Fi 6E / Wi-Fi 7 only.
                                                            Requires WPA3

   Lower frequency = travels further and through walls better, but slower.
```

### Wi-Fi Generations

| Standard | Marketing name | Bands | Approx. max speed |
|---|---|---|---|
| 802.11b | — | 2.4 GHz | 11 Mbps |
| 802.11a | — | 5 GHz | 54 Mbps |
| 802.11g | — | 2.4 GHz | 54 Mbps |
| 802.11n | **Wi-Fi 4** | 2.4 / 5 GHz | 600 Mbps |
| 802.11ac | **Wi-Fi 5** | 5 GHz | ~3.5 Gbps |
| 802.11ax | **Wi-Fi 6 / 6E** | 2.4 / 5 (/ 6 for 6E) GHz | ~9.6 Gbps |
| 802.11be | **Wi-Fi 7** | 2.4 / 5 / 6 GHz | ~46 Gbps |

> You don't need to memorize speeds for Security+. Just know that **802.11 = Wi-Fi** and that newer generations support newer security (WPA3).

---

## 📖 Wi-Fi Security: From Broken to Strong 🔐

## 🖼️ Figure 7.2 — The Wi-Fi Security Timeline

```
   1997          2003              2004                   2018
    │             │                 │                      │
    ▼             ▼                 ▼                      ▼
 ┌──────┐     ┌────────┐       ┌──────────────┐      ┌──────────────┐
 │ WEP  │ ──► │  WPA   │ ───►  │    WPA2      │ ───► │    WPA3      │
 │ RC4  │     │ TKIP   │       │ AES-CCMP     │      │ AES + SAE    │
 └──────┘     └────────┘       └──────────────┘      └──────────────┘
   ❌ Broken    ❌ Weak            ✅ OK (still common)   ✅✅ Best
   cracked in   temporary fix     weak point: offline    password guessing
   minutes      for WEP           password guessing      can't be done offline;
                                  if passphrase weak     forward secrecy
```

| Protocol | Encryption | Status | Remember |
|---|---|---|---|
| **Open** | None | ❌ Anyone can read traffic (unless the site uses HTTPS) | Coffee-shop risk |
| **WEP** | RC4 | ❌ **Broken.** Never use | "**W**eak **E**ncryption **P**rotocol" (joke name) |
| **WPA** | TKIP | ❌ Deprecated | Stop-gap |
| **WPA2** | **AES-CCMP** | ✅ Acceptable | Passphrase handshake can be captured and guessed offline |
| **WPA3** | AES (GCMP/CCMP) + **SAE** | ✅ **Best choice** | SAE stops offline guessing |

### Personal vs Enterprise Mode

## 🖼️ Figure 7.3 — One Shared Password vs Everyone Has Their Own Key

```
   WPA2/WPA3-PERSONAL (PSK / SAE)          WPA2/WPA3-ENTERPRISE (802.1X)
   ───────────────────────────────          ─────────────────────────────────────
   Everyone shares ONE passphrase          Each person logs in with their OWN
   "CoffeeLover2024!"                      username + password (or certificate)

    💻 ─┐                                   💻 alice ─┐
    📱 ─┼─► 📶 AP  (checks passphrase)       📱 bob   ─┼─► 📶 AP ──► 🗄️ RADIUS server
    💻 ─┘                                   💻 carol ─┘        (checks each identity,
                                                                logs who connected)
   ✔ Simple, for homes & small offices     ✔ For businesses
   ✘ Someone leaves → change it for all    ✔ Disable one account, others unaffected
   ✘ Can't tell WHO did what               ✔ Accountability: you know who's who
```

- **PSK** = Pre-Shared Key (WPA2-Personal). **SAE** = Simultaneous Authentication of Equals (WPA3-Personal).
- **802.1X** with a **RADIUS** server is the enterprise standard, and it comes back in Chapter 30.

> ⚠️ **WPS (Wi-Fi Protected Setup)**, the "push the button / enter an 8-digit PIN" feature, has a design flaw that lets attackers brute-force the PIN. **Disable WPS.**

---

## 📖 Common Wi-Fi Threats (Preview)

| Threat | What happens | Picture it |
|---|---|---|
| **Rogue access point** | An unauthorized AP plugged into the company network | A stranger installs a secret back door |
| **Evil twin** | Attacker creates a fake AP with the **same SSID** as a real one | A fake "Free Airport Wi-Fi" that steals your logins |
| **Deauthentication attack** | Attacker sends fake "disconnect" messages to kick you off | Forces you to reconnect, maybe to the evil twin |
| **Jamming** | Radio noise drowns out the signal | Someone shouting so nobody can talk (denial of service) |
| **Eavesdropping / sniffing** | Capturing wireless traffic | Listening in the crowded room |

Full details in Chapter 25. Defenses in Chapter 34.

---

## 📖 Other Wireless Technologies

## 🖼️ Figure 7.4 — The Range Ladder

```
   NFC        RFID          Bluetooth        Wi-Fi             Cellular (4G/5G)     Satellite
   ~4 cm      cm → ~100 m   ~10 m (typical)  ~30–100 m         km (cell towers)     Global
   📱💳        🏷️             🎧               📶                 📡                    🛰️
   tap to     badges,       earbuds,         home/office       phones, IoT,         remote areas,
   pay        inventory     keyboards        networks          hotspots             ships, GPS
   ◄──────────────────────────────── distance grows ─────────────────────────────────►
```

### Bluetooth 🎧

- Short-range **PAN** for earbuds, keyboards, watches and cars.
- Devices must be **paired** first.
- Threats: **Bluejacking** (sending unwanted messages, mostly annoying) and **Bluesnarfing** (*stealing* data like contacts and photos, which is serious). *Memory trick: snarf = snatch.*
- Defense: turn Bluetooth off when not needed, set it to **non-discoverable**, and keep devices updated.

### NFC — Near-Field Communication 💳

- Works only when devices nearly **touch** (~4 cm): contactless payments, phone wallets, door access.
- Threats: an attacker very close by could **skim** or **relay** the signal.

### RFID — Radio-Frequency Identification 🏷️

- Tiny tags that respond to a reader: **employee access badges**, shop anti-theft tags, inventory, pet microchips.
- Threat: **RFID cloning**, where an attacker copies your badge by standing near you with a hidden reader (Chapter 26).

### Cellular 📡

- **4G (LTE)** and **5G** networks run by mobile carriers. Your phone's **SIM / eSIM** identifies you.
- Threats: **SIM swapping** (an attacker convinces your carrier to move your number to their SIM and then receives your SMS login codes). **Fake cell towers** ("IMSI catchers / stingrays").
- Phones can share their cellular connection as a **hotspot** (tethering). That can let laptops bypass company network controls.

### GPS & Infrared

- **GPS** gives location. It's used for **geofencing** (rules like "only allow logins from inside the office") and for finding lost phones.
- **Infrared (IR)** is old line-of-sight tech (TV remotes). It still shows up in some devices.

---

## 📖 Mobile Devices: Computers in Your Pocket 📱

Phones and tablets are full computers (Chapter 1) that are **always online**, **always with you**, and **easily lost**. That makes them a big security challenge.

## 🖼️ Figure 7.5 — Why Mobile Is Risky

```
                    ┌───────────────────────────┐
     Lost/stolen ──►│                           │◄── Malicious apps
                    │        SMARTPHONE         │
   Public Wi-Fi ───►│  email · banking · photos │◄── Smishing (SMS phishing)
                    │  company data · MFA app   │
    Bluetooth  ────►│                           │◄── Jailbreaking / rooting
                    └───────────────────────────┘
                               ▲
                      Personal + work data mixed together
```

| Term | Meaning | Why it's risky |
|---|---|---|
| **App store** | Official, vetted source of apps (Apple App Store, Google Play) | Safer, though not perfect |
| **Side-loading** | Installing apps from **outside** the official store | Apps aren't checked, a common malware route (very common on Android) |
| **Jailbreaking** (iOS) | Removing Apple's built-in restrictions | Turns off security protections. Device may stop getting updates |
| **Rooting** (Android) | Gaining full **root/admin** access on Android | Same idea: apps can get unlimited power |
| **Carrier unlocking** | Using the phone with any mobile network | Not a security issue by itself (different from jailbreaking!) |
| **MDM** | **Mobile Device Management**: company software that controls phones (enforce PIN, encrypt, remote wipe) | The main defense (Chapter 34) |

### Who Owns the Phone? (Deployment Models Preview)

| Model | Meaning |
|---|---|
| **BYOD**: Bring Your Own Device | Employee's personal phone used for work. Cheapest for the company, hardest to control |
| **COPE**: Corporate-Owned, Personally Enabled | Company owns it, but you may use it personally |
| **CYOD**: Choose Your Own Device | You pick from an approved list; the company owns it |

These come back in Chapter 34.

---

## 🧠 Memory Tricks

- **Security order: "WEP < WPA < WPA2 < WPA3"**, newest is best. **WEP is dead.**
- **WPA2 = AES-CCMP · WPA3 = SAE.** ("SAE = Safer Against Eavesdroppers.")
- **Personal = one shared password. Enterprise = everyone has their own login (802.1X + RADIUS).**
- **Bluejacking = joking (messages). Bluesnarfing = snatching (data).**
- **Evil twin = same name, fake network.**
- **Jailbreak = iPhone. Root = Android.** Both remove protections.

---

## ⚠️ Exam Tip

- *"Which wireless security protocol should a company use for the strongest protection?"* → **WPA3** (Enterprise for businesses).
- *"Employees connect to an access point with the same SSID as the company's, but it is not the company's."* → **Evil twin.**
- *"Which method lets each employee authenticate to Wi-Fi with their own credentials?"* → **802.1X / WPA-Enterprise with RADIUS.**
- *"A user installed an app from a website instead of the app store."* → **Side-loading.**
- *"Which feature should be disabled because its PIN can be brute-forced?"* → **WPS.**

---

## 🧪 Try It (15 minutes)

1. **See nearby Wi-Fi networks and their security:**
   - Windows: `netsh wlan show networks mode=bssid` (shows SSID, BSSID, channel and authentication type).
   - macOS: hold **Option** and click the Wi-Fi icon to see the security type and channel.
   - Android: try a free Wi-Fi analyzer app.
   Which networks around you use WPA2? WPA3? Any open or WEP networks?
2. **Check your own router:** log in (often `192.168.1.1` or `192.168.0.1`). Is it using WPA2 or WPA3? Is **WPS** turned off? Did you change the **default admin password**?
3. **Phone check:** Is your phone's Bluetooth set to discoverable? Is the screen lock on? Is "install unknown apps" disabled?

---

## ✅ Checkpoint Questions

1. What is an SSID?
2. Why is wireless traffic easier to eavesdrop on than wired traffic?
3. Put these in order from weakest to strongest: WPA2, WEP, WPA3, WPA.
4. What is the main difference between WPA2-Personal and WPA2-Enterprise?
5. Which server checks each user's identity in enterprise Wi-Fi?
6. What is an evil twin?
7. What is the difference between bluejacking and bluesnarfing?
8. Which wireless technology only works within a few centimeters and is used for tap-to-pay?
9. What is the difference between jailbreaking and side-loading?
10. An attacker convinces your mobile carrier to move your phone number to their SIM. What is this attack, and why is it dangerous?

<details>
<summary><b>Show answers</b></summary>

1. The **name** of a wireless network.
2. Radio signals spread in all directions, **through walls and outside the building**, so anyone in range can capture them.
3. **WEP → WPA → WPA2 → WPA3.**
4. **Personal** uses one **shared passphrase**. **Enterprise** uses **802.1X** so each user logs in with their **own credentials** via a RADIUS server.
5. A **RADIUS** server (the authentication server).
6. A **fake access point** using the **same SSID** as a legitimate one, to trick people into connecting.
7. **Bluejacking** sends unwanted messages (annoying). **Bluesnarfing** steals data (serious).
8. **NFC.**
9. **Jailbreaking** removes the OS's built-in restrictions. **Side-loading** installs apps from outside the official store. (Jailbreaking often makes side-loading possible.)
10. **SIM swapping.** The attacker receives your **SMS codes**, so they can bypass SMS-based MFA and take over accounts.

</details>

### 🎯 Exam-Style Practice (multiple choice)

**MC1.** A 40-person office uses WPA2-Personal with one shared passphrase. An employee who knew it was just fired, and the manager also wants to know which person each connection belongs to. What is the BEST long-term fix?
A. Hide the SSID  B. Switch the AP to the 6 GHz band  C. Move to WPA2/WPA3-Enterprise (802.1X with RADIUS) so each user has their own login  D. Enable WPS so new users can join with a PIN

**MC2.** At an airport, a traveler's laptop keeps getting kicked off the Wi-Fi. Each time, it reconnects to a network with the same name but a stronger signal. Which attack is MOST likely causing the disconnections?
A. Bluejacking  B. Jamming the whole band  C. SIM swapping  D. A deauthentication attack

**MC3.** An employee's door badge was copied by someone who stood about a meter behind them in a coffee queue holding a hidden reader. Which technology was MOST likely abused?
A. RFID  B. NFC  C. Infrared  D. GPS

**MC4.** From the parking lot, an attacker captures the handshake of a laptop joining a WPA2-Personal network. What is the attacker MOST likely to do next?
A. Read the traffic immediately, because WPA2 uses no encryption  B. Use the handshake to clone the AP's BSSID  C. Try to guess the passphrase offline, which works well if the passphrase is weak  D. Nothing, because WPA2 handshakes cannot be captured

**MC5.** An employee connects their work laptop to their phone's hotspot to reach websites the office blocks. What is the MAIN security risk?
A. The phone's battery may run out  B. The laptop will switch to WEP  C. The phone becomes jailbroken  D. The laptop's traffic bypasses the company's network security controls

**MC6.** An administrator is installing three access points on the 2.4 GHz band and wants them not to interfere with each other. Which channels should be used?
A. 1, 2 and 3  B. 1, 6 and 11  C. 2, 4 and 6  D. 6, 7 and 8

<details>
<summary><b>Show multiple-choice answers</b></summary>

| # | Answer | Why |
|---|---|---|
| MC1 | C | Enterprise mode gives each person their own credentials, so one account can be disabled and connections are tied to a user; a hidden SSID is still found easily. |
| MC2 | D | Deauthentication attacks send fake "disconnect" messages, often to push victims onto an evil twin; jamming would block all connections. |
| MC3 | A | Badges use RFID, which can be read from several centimeters up to about 100 m; NFC only works within about 4 cm. |
| MC4 | C | A captured WPA2-Personal handshake can be attacked offline by guessing passphrases; WPA3's SAE was designed to stop exactly this. |
| MC5 | D | A hotspot gives the laptop a separate path to the internet that skips the company's firewall and web filtering. |
| MC6 | B | The 2.4 GHz band has only three non-overlapping channels: 1, 6 and 11. |

</details>


---

## 📌 Chapter Summary

| Topic | Key fact | Security link |
|---|---|---|
| Wi-Fi (802.11) | 2.4 / 5 / 6 GHz bands; SSID = name | Signal leaks outside walls |
| WEP → WPA3 | WPA3 (SAE) is best; WEP broken | Choose WPA3, disable WPS |
| Personal vs Enterprise | Shared passphrase vs 802.1X + RADIUS | Accountability, easy revocation |
| Bluetooth | ~10 m PAN | Bluejacking / bluesnarfing |
| NFC / RFID | cm-range tap / badge tags | Skimming, badge cloning |
| Cellular | 4G/5G, SIM | SIM swapping |
| Mobile devices | Always on, easily lost | Side-loading, jailbreaking, MDM |

**Next chapter →** *Chapter 8: Servers, Data Centers, Virtualization & Cloud.* Where do websites and company apps actually live? Let's visit the "computers that serve."
