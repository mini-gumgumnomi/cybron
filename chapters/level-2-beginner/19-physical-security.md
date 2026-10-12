# Chapter 19 — Physical Security

**Level 2 · Beginner for the Exam** · *Exam objective 1.2 (physical security)*

---

## 🎯 Goal

By the end of this chapter you will know every physical security control named in Security+: **bollards, access control vestibules, fencing, video surveillance, security guards, access badges, lighting** and **sensors** (infrared, pressure, microwave, ultrasonic). You'll also see how they're layered from the parking lot to the server room, and how attackers try to get around them.

---

## 🏠 Real-Life Story: Protecting a Castle 🏰

A medieval castle didn't rely on one big door. It had:
- a **moat** and **walls** to keep people away,
- a **drawbridge** with a **gatehouse** where guards checked visitors,
- **torches** so nobody could sneak up in the dark,
- **lookouts** on the towers,
- and the treasure locked in the **innermost room**.

Modern buildings work exactly the same way. Each layer **slows down, discourages, detects or stops** an intruder. If you can **touch** the server, firewalls and passwords don't matter, because you can simply steal the disk.

---

## 🖼️ Figure 19.1 — Layers from the Street to the Server

```
 ┌───────────────────────────────────────────────────────────────────────────┐
 │ LAYER 1 - PERIMETER: fencing, bollards, lighting, signs, cameras          │
 │  ┌─────────────────────────────────────────────────────────────────────┐  │
 │  │ LAYER 2 - GROUNDS: parking controls, guards on patrol, sensors      │  │
 │  │  ┌───────────────────────────────────────────────────────────────┐  │  │
 │  │  │ LAYER 3 - BUILDING ENTRANCE: reception, guards, badge readers,│  │  │
 │  │  │           access control vestibule, visitor logs              │  │  │
 │  │  │  ┌─────────────────────────────────────────────────────────┐  │  │  │
 │  │  │  │ LAYER 4 - INTERIOR: badge doors per floor/zone, cameras │  │  │  │
 │  │  │  │  ┌───────────────────────────────────────────────────┐  │  │  │  │
 │  │  │  │  │ LAYER 5 - SERVER ROOM: badge + PIN/biometric,     │  │  │  │  │
 │  │  │  │  │           locked racks, sensors, logs             │  │  │  │  │
 │  │  │  │  └───────────────────────────────────────────────────┘  │  │  │  │
 │  │  │  └─────────────────────────────────────────────────────────┘  │  │  │
 │  │  └───────────────────────────────────────────────────────────────┘  │  │
 │  └─────────────────────────────────────────────────────────────────────┘  │
 └───────────────────────────────────────────────────────────────────────────┘
```

---

## 📖 Part 1 — Perimeter Controls 🚧

### Bollards
Short, **strong posts** (concrete or steel) placed in front of buildings and entrances.
- **Purpose:** stop **vehicles** from ramming into the building, while still letting **people walk through**.
- Often disguised as planters or benches.
- Control type: **Preventive** (physical).

### Fencing
- Marks the boundary and **keeps people out**.
- Height matters: about **1 m** deters casual walkers; **2.5 m+ with barbed/razor wire on top** stops determined climbers.
- Control type: **Preventive** and **Deterrent**.

### Lighting 💡
- Bright lighting removes hiding places and **helps cameras** record clear images.
- Control type: **Deterrent** (and supports detection).

### Signs 🪧
- "Private Property," "CCTV in operation," "Authorized Personnel Only."
- Control type: **Deterrent** and **Directive**.

---

## 📖 Part 2 — People and Entry Controls 🚪

### Security Guards 💂
- **Flexible**: they can make judgment calls, check IDs, escort visitors and respond to alarms.
- Can be **preventive, deterrent, detective and corrective** all at once.
- **Two-person integrity / two-person control:** some areas require **two guards or staff together**, so no single person can act alone (protects against insider threats).

### Access Badges 🪪
- ID cards (often **RFID** or **NFC**, Chapter 7) that open doors and **log who entered and when** (accounting!).
- Usually show a **photo**, so guards can check it matches the person.
- Risk: **badge cloning** (copying the RFID signal, Chapter 26) and **lost/stolen badges**. Combine with a PIN or biometric for sensitive areas.

### Access Control Vestibule (formerly "mantrap") 🔁
A small room with **two doors**. **Only one door can be open at a time.** You must be authenticated at the first door, enter, wait for it to close, then authenticate at the second door.

## 🖼️ Figure 19.2 — How an Access Control Vestibule Stops Tailgating

```
        OUTSIDE              VESTIBULE                INSIDE (secure area)
                        ┌──────────────────┐
 You ──badge──► Door A ─│  YOU (only one   │─ Door B ──badge/PIN──► Secure area
                        │  person fits, or │
                        │  a sensor/guard  │
                        │  checks)         │
                        └──────────────────┘
     Door A must CLOSE before Door B can OPEN.
     If someone tries to follow you in, you're both trapped between the doors
     until a guard checks.
```

### Locks 🔒

| Lock type | How it opens | Notes |
|---|---|---|
| **Traditional key lock** | Physical key | Keys can be copied; locks can be picked |
| **Combination / keypad (cipher) lock** | A code | Codes get shared; shoulder surfing |
| **Electronic badge lock** | Badge/card | Logs entries; can revoke a lost badge instantly |
| **Biometric lock** | Fingerprint, face, iris | Hard to share; FAR/FRR issues (Chapter 17) |

### Visitor Management 📋
- **Visitor logs** (sign in and out), **temporary visitor badges**, and **escorts** at all times in secure areas.

---

## 📖 Part 3 — Detection Controls 📹

### Video Surveillance (CCTV) 🎥
- **Records** who came and went (**detective**). **Visible** cameras also **deter**.
- Modern systems include **motion detection**, **object detection** (e.g., spotting a left bag or a person climbing a fence), facial recognition, and **remote viewing**.
- Placement matters: entrances, exits, server rooms, parking lots. Avoid blind spots, and use good lighting.

### Sensors 📡 (four types named in SY0-701)

| Sensor | How it detects | Typical use |
|---|---|---|
| **Infrared (IR)** | Detects **body heat** / changes in infrared light | Motion detectors in rooms and hallways; turning on lights/alarms |
| **Pressure** | Detects **weight/force** on a surface | Floor mats, under-carpet pads, fence lines, windows |
| **Microwave** | Sends **microwave pulses** and measures reflections (like radar) | Covers **larger areas**, can sense through some materials |
| **Ultrasonic** | Sends **high-frequency sound waves** and detects echo changes | Room motion detection, parking sensors |

> 💡 Sensors are **detective** controls. They usually trigger **alarms** or **cameras**, which a guard then responds to.

---

## 📖 Part 4 — Physical Attacks to Know 🦹

| Attack | What happens | Defense |
|---|---|---|
| **Tailgating** | Following an authorized person through a door **without their knowledge/consent** | Access control vestibules, turnstiles, training ("one badge, one person") |
| **Piggybacking** | Same thing, but the authorized person **knowingly lets** them in (e.g., holds the door) | Training, policy, vestibules |
| **Badge cloning** | Copying an RFID badge with a hidden reader | Encrypted smart cards, badge + PIN, RFID-blocking sleeves |
| **Lock picking / brute force** | Forcing or picking locks, breaking windows | Strong locks, sensors, cameras, guards |
| **Shoulder surfing** | Watching someone enter a PIN or password | Privacy screens, shielded keypads |
| **Dumpster diving** | Searching the trash for documents, hardware | **Shredding**, locked bins, secure disposal |
| **Theft of devices** | Stealing laptops, phones, drives | Cable locks, **full-disk encryption**, asset tracking |
| **Environmental** | Fire, flood, power loss, extreme heat (deliberate or natural) | Fire suppression, HVAC, UPS/generators, water sensors |

> ⚠️ **Tailgating vs piggybacking:** many books treat them as the same thing. When they're separated: **tailgating = without permission (sneaky)**, **piggybacking = with permission (the insider helps)**.

---

## 📖 Part 5 — Protecting the Equipment Itself 🖥️

| Control | Purpose |
|---|---|
| **Locked server racks / cabinets** | Even people inside the server room can't touch every server |
| **Cable locks** | Stop laptops being carried away |
| **Faraday cage** | A metal mesh enclosure that **blocks radio signals** (used for sensitive rooms or for holding seized phones in forensics) |
| **Screen filters / privacy screens** | Stop shoulder surfing |
| **Secure disposal** | Shredding papers; wiping, degaussing or physically destroying drives (Chapter 35) |
| **Environmental controls** | Fire suppression (gas systems in server rooms, because water damages electronics), cooling (HVAC), humidity control, UPS and generators |
| **Clean desk policy** | No sensitive papers or passwords left on desks |

---

## 📖 Part 6 — Classifying Physical Controls (link to Chapter 13)

| Control | Category | Type(s) |
|---|---|---|
| Bollards | Physical | Preventive |
| Fence | Physical | Preventive, Deterrent |
| Lighting | Physical | Deterrent (supports Detective) |
| "Authorized Personnel Only" sign | Physical | Directive, Deterrent |
| Security guard | Operational (a person) / Physical | Preventive, Deterrent, Detective, Corrective |
| Access control vestibule | Physical | Preventive |
| Badge reader logs | Technical/Physical | Detective (accounting) |
| CCTV | Physical | Detective (+ Deterrent if visible) |
| Motion sensor (IR, microwave…) | Physical | Detective |
| Fire suppression system | Physical | Corrective |

---

## 🧠 Memory Tricks

- **Bollards = "bump stops for cars."**
- **Vestibule = "two doors, one at a time."**
- **Sensors: "I Pressed My Ultrasound"**: **I**nfrared (heat), **P**ressure (weight), **M**icrowave (radar), **U**ltrasonic (sound).
- **Tailgate = sneak in behind. Piggyback = given a ride (with permission).**
- **Lights + cameras + signs = "Don't even try" (deterrents).**

---

## ⚠️ Exam Tip

- *"Which control BEST prevents a vehicle from crashing into the lobby?"* → **Bollards.**
- *"Which control BEST prevents tailgating into a data center?"* → **Access control vestibule.**
- *"A sensor detects body heat in a room after hours."* → **Infrared sensor.**
- *"Which control provides a record of who entered a room?"* → **Badge access logs** (or video surveillance).
- *"An employee held the door open for a 'delivery person' who had no badge."* → **Piggybacking/tailgating** (social engineering).
- Remember: a **guard** is the most **flexible** control, because guards can think and adapt.

---

## 🧪 Try It (15 minutes)

1. **Walk-around audit:** walk around your workplace, school or apartment building. List every physical control you see, from the outside in. Label each with its **type** (preventive, deterrent, detective…).
2. **Spot the weak points:** Is any door propped open? Are cameras missing anywhere? Can you see anyone's screen from a public area? Is there a shredder?
3. **Sensor hunt:** find motion sensors (often small white boxes high in corners). Are they infrared? (Most indoor ones are passive infrared, "PIR.")

---

## ✅ Checkpoint Questions

1. What are bollards designed to stop?
2. How does an access control vestibule prevent tailgating?
3. What's the difference between tailgating and piggybacking?
4. Name the four sensor types in SY0-701 and what each detects.
5. Which physical control is the most flexible, and why?
6. Is visible CCTV a preventive, deterrent or detective control?
7. Why do server rooms often use gas-based fire suppression instead of water sprinklers?
8. What is two-person integrity?
9. Name two ways to protect against stolen access badges being misused.
10. What is the purpose of lighting in physical security?

<details>
<summary><b>Show answers</b></summary>

1. **Vehicles** (ramming attacks) from reaching buildings or entrances.
2. **Only one door opens at a time**, and each person must authenticate, so an extra person gets trapped between the doors.
3. **Tailgating** = following someone in **without** their knowledge or consent. **Piggybacking** = the authorized person **knowingly** lets them in.
4. **Infrared** (body heat), **pressure** (weight/force), **microwave** (reflected microwave pulses), **ultrasonic** (reflected sound waves).
5. **Security guards.** They can use judgment, adapt to situations and respond.
6. **Detective** (it records) and **deterrent** (it's visible). It does **not** physically prevent entry.
7. **Water damages electronic equipment.** Gas systems put out fires without destroying the servers.
8. A rule requiring **two people to be present** for a sensitive task or area, so no single person can act alone.
9. E.g., **revoke the badge immediately** when reported lost; require **badge + PIN or biometric**; check the badge **photo** against the person.
10. To **deter** intruders, remove hiding places, and help **cameras** capture clear images.

</details>

### 🎯 Exam-Style Practice (multiple choice)

**MC1.** A museum wants an alarm to sound if anyone steps on the floor directly in front of a display case after closing time. Which sensor type BEST fits?
A. Infrared  B. Microwave  C. Ultrasonic  D. Pressure

**MC2.** A forensic team seizes a suspect's phone and must stop it from receiving a remote-wipe command before it is examined. What should they place it in?
A. A locked server rack  B. An access control vestibule  C. A Faraday bag or cage  D. A safe with a combination lock

**MC3.** A company stores its backup encryption keys in a vault that opens only when two named staff members are present together. What is the MAIN purpose of this rule?
A. No single person can access the keys alone, which protects against an insider acting alone  B. It makes the vault open faster  C. It replaces the need for any logging  D. It stops vehicles from reaching the vault

**MC4.** Attackers cloned an employee's RFID badge using a hidden reader. Which change BEST stops a cloned badge ALONE from opening the server room?
A. Brighter lighting outside the building  B. Adding a "No entry" sign  C. Requiring badge plus PIN or biometric at the server room door  D. Moving the badge readers lower on the wall

**MC5.** An auditor finds printed customer lists in an open recycling bin behind the office. Which attack does this expose the company to, and what is the BEST fix?
A. Tailgating; install bollards  B. Badge cloning; use RFID sleeves  C. Shoulder surfing; use privacy screens  D. Dumpster diving; shred documents and use locked bins

**MC6.** HVAC contractors need regular access to the server room to service the cooling units. Which control BEST stops them from touching the servers while they work?
A. A fence around the car park  B. Locked server racks or cabinets  C. Ultrasonic motion sensors  D. A visitor sign-in sheet only

<details>
<summary><b>Show multiple-choice answers</b></summary>

| # | Answer | Why |
|---|---|---|
| MC1 | D | Pressure sensors detect weight or force on a surface such as a floor mat; infrared detects body heat in a whole area. |
| MC2 | C | A Faraday bag or cage blocks radio signals, so the phone cannot receive a remote-wipe command. |
| MC3 | A | Two-person integrity means no one person can act alone, reducing the insider threat. |
| MC4 | C | A second factor (PIN or biometric) means a copied badge alone is not enough to get in. |
| MC5 | D | Searching the trash is dumpster diving; shredding and locked bins are the standard defense. |
| MC6 | B | Locked racks protect equipment even from people who are allowed into the room; a sign-in sheet only records visits. |

</details>


---

## 📌 Chapter Summary

| Control | One-liner |
|---|---|
| Bollards | Stop vehicles, let people through |
| Fencing | Mark and protect the perimeter |
| Lighting | Deter and support cameras |
| Security guards | Most flexible: prevent, deter, detect, respond |
| Access badges | Open doors + log entries; risk of cloning |
| Access control vestibule | Two doors, one at a time; stops tailgating |
| Video surveillance | Detect and record (deter if visible) |
| Sensors | Infrared (heat), pressure (weight), microwave (radar), ultrasonic (sound) |

**Next chapter →** *Chapter 20: Defense in Depth & Your First Security Tools.* Physical layers are one part of the picture. Let's stack all the layers together.
