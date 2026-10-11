# Chapter 32 — Resilience & Recovery

**Level 3 · Can Score ~40%** · *Exam objective 3.4*

---

## 🎯 Goal

By the end of this chapter you will know how organizations **stay running** and **recover** after failures, attacks and disasters:
- **High availability:** load balancing vs clustering
- **Site considerations:** hot, warm and cold sites; geographic dispersion
- **Platform diversity**, **multi-cloud systems**, **continuity of operations**
- **Capacity planning:** people, technology, infrastructure
- **Testing:** tabletop exercises, failover, simulation, parallel processing
- **Backups:** onsite/offsite, frequency, encryption, snapshots, recovery, replication, journaling
- **Power:** generators, UPS

---

## 🏠 Real-Life Story: The Wedding Day Plan 💍

A wedding planner can't say "sorry, the caterer got sick, wedding cancelled." So they plan for failure:
- **Two caterers on standby** (redundancy).
- **A backup venue** booked: one fully set up and ready (**hot site**), one with tables but no decorations (**warm site**), or just an empty hall they could use if desperate (**cold site**).
- **A generator** in case the venue's power fails.
- **Copies of the guest list** in three places (**backups**).
- **A rehearsal** the day before (**testing**).

**Resilience** = the ability to **keep going** when things break. **Recovery** = getting back to normal **afterwards**.

---

## 📖 Part 1 — High Availability: Load Balancing vs Clustering ⚖️

Both use **multiple servers**, but in different ways.

## 🖼️ Figure 32.1 — Load Balancing vs Clustering

```
   LOAD BALANCING                                   CLUSTERING
   (spread the work)                                (servers act as ONE system)

          users                                            users
            │                                                │
     ┌──────┴───────┐                                ┌───────┴────────┐
     │ LOAD BALANCER│                                │ CLUSTER (one    │
     └──┬────┬───┬──┘                                │ virtual address)│
        ▼    ▼   ▼                                   └───┬────────┬───┘
      [S1] [S2] [S3]   independent servers,              ▼        ▼
                       each handles some requests      [Node A]◄──►[Node B]
                       If S2 dies, the LB stops          share storage/state,
                       sending traffic to it.            heartbeat between nodes.
                                                         If A fails, B takes over
                                                         (FAILOVER).
```

| | **Load balancing** | **Clustering** |
|---|---|---|
| Idea | **Distribute** requests across several independent servers | Several servers **work together as one**, sharing state/storage |
| Good for | Web servers, stateless apps; **performance + availability** | Databases, stateful apps that need **failover** |
| Modes | Active/active (all serve) | Active/passive (standby takes over) or active/active |
| Failure | Failed server removed from the pool (health checks) | Another node takes over the workload |

### Redundancy Building Blocks 🧱
- **RAID** (Redundant Array of Independent Disks):
  - **RAID 0** = striping across disks for speed, **no redundancy** (one disk dies → all data lost)
  - **RAID 1** = **mirroring** (exact copy on two disks)
  - **RAID 5** = striping **with parity** (needs at least 3 disks, survives **1** disk failure)
  - **RAID 6** = **double parity** (survives **2** disk failures)
  - **RAID 10** = mirroring + striping
- **Redundant power supplies, NICs, network paths, internet providers.**
- Goal: **no single point of failure (SPOF).**

---

## 📖 Part 2 — Site Considerations 🏢

If the main site is destroyed (fire, flood, earthquake), where do you go?

## 🖼️ Figure 32.2 — Hot, Warm and Cold Sites

```
   🔥 HOT SITE                      🌤️ WARM SITE                      🧊 COLD SITE
   "Move in today"                  "Furnished, needs set-up"         "Empty building"
   ┌──────────────────────┐        ┌──────────────────────┐          ┌──────────────────────┐
   │ Hardware: ✔ running  │        │ Hardware: ✔ some     │          │ Hardware: ✘ none     │
   │ Software: ✔ installed│        │ Software: ~ partial  │          │ Software: ✘ none     │
   │ Data:     ✔ live /   │        │ Data:     ✘ restore  │          │ Data:     ✘ restore  │
   │           near-live  │        │           from backup│          │           from backup│
   │ Power/net: ✔         │        │ Power/net: ✔         │          │ Power/net: ✔ (basic) │
   └──────────────────────┘        └──────────────────────┘          └──────────────────────┘
   Recovery: MINUTES-HOURS          Recovery: HOURS-DAYS              Recovery: DAYS-WEEKS
   Cost:     $$$$ (highest)         Cost:     $$                      Cost:     $ (lowest)
```

| Site | Ready? | Recovery time | Cost |
|---|---|---|---|
| **Hot** | Fully equipped, **data replicated**, can take over almost immediately | Fastest | Highest |
| **Warm** | Equipment and connectivity in place, but **data must be restored** and systems configured | Medium | Medium |
| **Cold** | Just **space, power and cooling**. Everything else must be brought in | Slowest | Lowest |
| (also) **Mobile site** | A trailer/container data center driven to where it's needed | Varies | Varies |
| (also) **Cloud-based DR** | Recovery environment in the cloud, spun up when needed | Can be fast | Pay-per-use |

### Geographic Dispersion 🌍
Put backup sites (and data copies) **far enough away** that **one disaster can't hit both**: a hurricane, regional power outage or earthquake shouldn't take out the primary **and** the backup. Balance against **data sovereignty** laws (Chapter 31) and latency.

---

## 📖 Part 3 — Platform Diversity & Multi-Cloud 🎲

- **Platform diversity:** using **different technologies** (vendors, operating systems, products) so **one flaw or outage can't take down everything**. Example: two firewalls from different vendors in layers; mixing OSes so a single worm can't infect all servers.
  - Trade-off: more complexity, more skills needed.
- **Multi-cloud systems:** spreading workloads across **more than one cloud provider** (e.g., AWS + Azure), so a provider-wide outage or problem doesn't stop the business, and to avoid **vendor lock-in**.
  - Trade-off: complexity, consistent security policies are harder, higher costs.

---

## 📖 Part 4 — Continuity of Operations & Capacity Planning 📋

### Continuity of Operations (COOP)
Plans and procedures that keep **essential functions** running during and after a disruption: who does what, where staff work, alternate processes (even **manual/paper** workarounds), communication plans.
> Related plans (Chapter 43): **Business Continuity Plan (BCP)** = keep the whole business running. **Disaster Recovery Plan (DRP)** = restore IT systems.

### Capacity Planning 📈
Making sure you have **enough resources** to handle normal load, peaks and recovery situations.

| Area | Questions |
|---|---|
| **People** | Enough trained staff? Cross-training if key people are unavailable? Who's on call during a disaster? |
| **Technology** | Enough server/software capacity and licenses if load doubles or one site fails? |
| **Infrastructure** | Enough bandwidth, power, cooling, rack space, and cloud quotas at the recovery site? |

---

## 📖 Part 5 — Testing the Plans 🧪

**A plan that's never been tested is just a hope.**

| Test type | What happens | Disruption | Realism |
|---|---|---|---|
| **Tabletop exercise** | Key people sit around a table and **talk through** a scenario step by step ("Ransomware hits at 9 am, what do we do?") | None | Low |
| **Simulation** | A realistic **practice scenario** is acted out (e.g., a simulated phishing outbreak or a mock disaster), without touching production systems | Low | Medium |
| **Parallel processing** | The backup/recovery system is brought up and runs **at the same time as** the primary, processing the same work, so results can be compared | Low | High |
| **Fail over** (failover test) | Actually **switch production** to the backup system/site to prove it works | Can be high | Highest |

## 🖼️ Figure 32.3 — The Testing Ladder

```
   REALISM & RISK ▲
                  │   FAILOVER          "switch production over for real"
                  │   PARALLEL          "run backup alongside primary"
                  │   SIMULATION        "act it out, no production impact"
                  │   TABLETOP          "talk it through around a table"
                  └─────────────────────────────────────────────► COST & EFFORT
```

---

## 📖 Part 6 — Backups 💾 (the #1 recovery tool)

### Backup Types

## 🖼️ Figure 32.4 — Full, Incremental, Differential

```
   Data changes each day: Mon(full) ... Tue +A ... Wed +B ... Thu +C

                     Mon        Tue          Wed            Thu
   FULL              [ALL]      [ALL+A]      [ALL+A+B]      [ALL+A+B+C]   big & slow every day
   INCREMENTAL       [ALL]      [A]          [B]            [C]           only changes since
                                                                          the LAST backup (any type)
   DIFFERENTIAL      [ALL]      [A]          [A+B]          [A+B+C]       all changes since
                                                                          the LAST FULL backup

   RESTORE on Thursday after a crash:
     Incremental  → Mon full + Tue + Wed + Thu   (fast backups, SLOWER restore: 4 sets)
     Differential → Mon full + Thu               (slower backups, FASTER restore: 2 sets)
```

| Type | Backs up | Backup speed | Restore needs |
|---|---|---|---|
| **Full** | Everything | Slowest | Just the full backup |
| **Incremental** | Changes since the **last backup of any kind** | Fastest | Last full + **every** incremental since |
| **Differential** | Changes since the **last full** backup | Medium (grows daily) | Last full + **the latest** differential |

### Backup Considerations in SY0-701

| Consideration | Meaning / best practice |
|---|---|
| **Onsite vs offsite** | Onsite = fast restores. Offsite (another location or cloud) = survives a site disaster. **Do both.** |
| **Frequency** | How often to back up, driven by the **RPO**: how much data loss is acceptable (Chapter 44). Hourly? Daily? |
| **Encryption** | Backups contain **all your data**, so encrypt them (and protect the keys). Stolen unencrypted backup tapes are a classic breach |
| **Snapshots** | A **point-in-time image** of a system/VM/volume, taken almost instantly. Great for quick rollback (e.g., before patching). Usually stored on the same system, so **not a replacement for real backups** |
| **Recovery** | **Test restores regularly.** A backup you can't restore is worthless. Know how long recovery takes (RTO) |
| **Replication** | **Continuously copying** data to another system/site (synchronous = real-time; asynchronous = slight delay). Great for availability, **but it also copies corruption and ransomware-encrypted files!** |
| **Journaling** | Recording **every change in a log (journal)** so data can be **replayed or rolled back** to any point in time; used by databases and file systems |

> ⚠️ **Replication is not a backup.** If ransomware encrypts the primary, replication faithfully copies the encrypted files to the replica. You still need **point-in-time, offline/immutable backups**.

### The 3-2-1 Rule 🥇

```
   3  copies of your data (the original + 2 backups)
   2  different types of media/storage
   1  copy OFFSITE (and ideally one OFFLINE or IMMUTABLE, i.e. "3-2-1-1")
```

---

## 📖 Part 7 — Power ⚡

## 🖼️ Figure 32.5 — Power Failure Timeline

```
   Mains power fails ───────────────────────────────────────────────────────►
        │
        0 s      UPS batteries take over INSTANTLY (no interruption)
        │        UPS covers seconds to minutes ("bridge" time)
        │
        ~10-60 s Generator starts and stabilizes
        │        Transfer switch moves the load to the generator
        │
        hours+   Generator runs as long as there's FUEL
        │
   Mains power returns → load moves back → generator stops → UPS recharges
```

| Device | Purpose | Duration |
|---|---|---|
| **UPS** (Uninterruptible Power Supply) | Batteries provide **instant**, clean power. Bridges the gap until the generator starts, or allows a **graceful shutdown**; also smooths spikes and sags | Minutes |
| **Generator** | Fuel-powered (diesel/gas) **long-term** power | Hours to days (fuel-dependent) |
| (also) **PDU** (Power Distribution Unit) | Distributes power to rack equipment; "smart" PDUs allow monitoring | — |
| (also) **Dual power supplies + separate circuits** | Redundancy inside each server | — |

---

## 🧠 Memory Tricks

- **Load balancing = share the work. Clustering = act as one.**
- **Hot = ready now. Warm = needs data. Cold = empty room.** (Cost goes down as temperature goes down.)
- **Incremental = since the last backup. Differential = since the last FULL** ("**D**ifferential = **D**ifference from full").
- **Restore: Incremental = all the pieces. Differential = full + latest.**
- **Replication ≠ backup** (it copies the ransomware too!).
- **UPS = seconds to minutes (instant). Generator = hours (needs fuel).**
- **Tests from gentle to real: Talk (tabletop) → Act (simulation) → Run alongside (parallel) → Switch over (failover).**

---

## ⚠️ Exam Tip

- *"Which site can take over operations within minutes but is the most expensive?"* → **Hot site.**
- *"Which backup type requires only the last full and the most recent backup to restore?"* → **Differential.**
- *"Which provides immediate power until the generator starts?"* → **UPS.**
- *"Managers walk through a ransomware scenario in a conference room."* → **Tabletop exercise.**
- *"Why isn't replication enough to recover from ransomware?"* → It **replicates the encrypted/corrupted data** too.
- *"A company uses two different cloud providers to avoid a single provider outage."* → **Multi-cloud.**
- *"Using firewalls from two different vendors so one vulnerability doesn't affect both."* → **Platform diversity.**
- *"Which is the BEST way to make sure backups will work?"* → **Regularly test restores.**

---

## 🧪 Try It (20 minutes)

1. **Back up your own data with 3-2-1:** original on your laptop + a copy on an external drive (2 media) + a cloud copy (offsite). Then **test a restore** of one file.
2. **Take a VM snapshot** in VirtualBox, change something, and roll back (snapshot = quick point-in-time restore).
3. **Run a tabletop on yourself:** "My laptop is stolen today." Write down every step: what do you lose, what accounts must you secure, how do you restore your files, how long does it take?
4. **Calculate the restore sets:** full backup Sunday, incrementals Mon–Fri, crash on Friday afternoon after Friday's backup. How many backup sets do you need? (Answer: **6**: Sunday full + 5 incrementals.) What if they were differentials? (**2**: Sunday full + Friday's differential.)

---

## ✅ Checkpoint Questions

1. What's the difference between load balancing and clustering?
2. Which RAID level provides mirroring? Which survives two disk failures?
3. Compare hot, warm and cold sites by readiness and cost.
4. Why is geographic dispersion important?
5. What is platform diversity, and what is its downside?
6. Name the three areas of capacity planning.
7. Put these tests in order from least to most disruptive: failover, tabletop, parallel processing, simulation.
8. What's the difference between incremental and differential backups?
9. Why isn't replication a substitute for backups?
10. What do a UPS and a generator each provide?

<details>
<summary><b>Show answers</b></summary>

1. **Load balancing** distributes requests across independent servers. **Clustering** makes multiple servers act as **one system** with shared state and failover.
2. **RAID 1** = mirroring. **RAID 6** survives two disk failures.
3. **Hot:** fully ready, data replicated, fastest, **most expensive**. **Warm:** equipment ready, data must be restored, medium. **Cold:** space/power only, slowest, **cheapest**.
4. So **one disaster can't destroy both** the primary and backup sites/data.
5. Using **different vendors/technologies** so one flaw or outage doesn't affect everything. Downside: **more complexity and skills required**.
6. **People, technology, infrastructure.**
7. **Tabletop → simulation → parallel processing → failover.**
8. **Incremental** backs up changes since the **last backup of any type**. **Differential** backs up all changes since the **last full** backup.
9. Replication **copies corruption, deletions and ransomware-encrypted files** to the replica. You need **point-in-time, offline/immutable backups**.
10. **UPS:** instant battery power for minutes (bridge or graceful shutdown). **Generator:** long-term power for as long as there's fuel.

</details>

---

## 📌 Chapter Summary

| Topic | Key points |
|---|---|
| High availability | Load balancing (spread) vs clustering (act as one); RAID; no SPOF |
| Sites | Hot (ready, $$$) · warm (needs data) · cold (empty, $); geographic dispersion |
| Diversity | Platform diversity, multi-cloud: avoid single points of failure and lock-in |
| Continuity | COOP; capacity planning for people, technology, infrastructure |
| Testing | Tabletop → simulation → parallel → failover |
| Backups | Full / incremental / differential; onsite + offsite; encrypt; snapshots; test restores; replication ≠ backup; journaling; 3-2-1 |
| Power | UPS (instant, minutes) → generator (hours, fuel) |

**Next chapter →** *Chapter 33: Change Management, Zero Trust & Deception.* The final Level 3 chapter: how to change systems safely, how "never trust, always verify" works, and how to trap attackers with honeypots.
