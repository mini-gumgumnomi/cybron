# Chapter 44 — Risk Management (with the Math)

**Level 4 · Advanced Knowledge** · *Exam objective 5.2*

---

## 🎯 Goal

By the end of this chapter you will be able to explain and calculate everything in the risk management process:
- **Risk identification** and **risk assessment** (ad hoc, recurring, one-time, continuous)
- **Risk analysis:** qualitative, quantitative, **SLE, ALE, ARO**, probability, likelihood, **exposure factor**, impact
- **Risk register:** key risk indicators (KRIs), risk owners, risk threshold
- **Risk tolerance** and **risk appetite** (expansionary, conservative, neutral)
- **Risk management strategies:** transfer, accept (exemption, exception), avoid, mitigate
- **Risk reporting**
- **Business impact analysis:** **RTO, RPO, MTTR, MTBF**

Expect **calculation questions**: the formulas here are guaranteed exam points if you practise them.

---

## 🏠 Real-Life Story: Should I Insure My Bike? 🚲

Your bike is worth **$1,000**. In your town, bikes get stolen about **once every 4 years** (0.25 times per year). If it's stolen, you lose the **whole** bike.

- Loss each time it happens: $1,000
- Expected loss per year: $1,000 × 0.25 = **$250**

Insurance costs **$400/year**. A good lock costs **$60 once** and cuts the theft rate to once every 10 years (expected loss **$100/year**).

You just did **quantitative risk analysis**: the lock is clearly better value than the insurance. Organizations do exactly this, with servers instead of bikes.

---

## 📖 Part 1 — Risk Identification & Assessment 🔍

### Risk Identification
Finding **what could go wrong**: list **assets**, **threats** and **vulnerabilities** (Chapter 10), using workshops, vulnerability scans, threat intelligence, audits, past incidents and BIAs.

### Types of Risk Assessment (by timing)

| Type | When | Example |
|---|---|---|
| **Ad hoc** | **As needed**, triggered by an event | A new vendor, a merger, a major incident, a new law |
| **Recurring** | On a **regular schedule** | Annual risk assessment, quarterly reviews |
| **One-time** | **Once**, for a specific project/purpose | Assessing a new data center before it opens |
| **Continuous** | **Ongoing, often automated** monitoring | Real-time risk dashboards, continuous vulnerability scanning, KRIs tracked live |

---

## 📖 Part 2 — Risk Analysis: Qualitative vs Quantitative ⚖️

| | **Qualitative** | **Quantitative** |
|---|---|---|
| Uses | **Words/ratings**: Low/Medium/High, 1–5 scales | **Numbers and money** ($) |
| Based on | Expert judgment, experience | Data: asset values, loss history, frequencies |
| ✅ | Fast, easy, works when data is missing | Objective, supports cost-benefit decisions |
| ❌ | Subjective | Needs good data; time-consuming |
| Output | **Heat map / risk matrix** | **ALE in dollars** |

## 🖼️ Figure 44.1 — Qualitative Heat Map (Likelihood × Impact)

```
                         IMPACT →
                   1 Minor   2 Moderate  3 Major   4 Severe
                 ┌─────────┬───────────┬─────────┬──────────┐
   L  4 Likely   │ Medium  │   High    │Critical │ Critical │
   I             ├─────────┼───────────┼─────────┼──────────┤
   K  3 Possible │  Low    │  Medium   │  High   │ Critical │
   E             ├─────────┼───────────┼─────────┼──────────┤
   L  2 Unlikely │  Low    │   Low     │ Medium  │   High   │
   I             ├─────────┼───────────┼─────────┼──────────┤
   H  1 Rare     │  Low    │   Low     │  Low    │  Medium  │
   O             └─────────┴───────────┴─────────┴──────────┘
   O
   D   e.g., ransomware: Possible (3) × Severe (4) → CRITICAL
```

**Probability vs likelihood:**
- **Probability**: a **measurable, numerical** chance (e.g., 0.25 = 25% per year), used in quantitative analysis.
- **Likelihood**: a more **general, often qualitative** estimate of how likely something is ("possible," "likely").
- **Impact**: the **size of the harm** if it happens (financial, reputational, legal, safety).

---

## 📖 Part 3 — The Quantitative Formulas ⭐⭐⭐

## 🖼️ Figure 44.2 — Formula Cards

```
   ┌─────────────────────────────────────────────────────────────┐
   │  AV  = ASSET VALUE (in $)                                   │
   │  EF  = EXPOSURE FACTOR: % of the asset lost in ONE event    │
   │        (0% – 100%, written as 0.0 – 1.0)                    │
   ├─────────────────────────────────────────────────────────────┤
   │  SLE = SINGLE LOSS EXPECTANCY  = AV × EF                    │
   │        "How much do we lose EACH TIME it happens?"          │
   ├─────────────────────────────────────────────────────────────┤
   │  ARO = ANNUALIZED RATE OF OCCURRENCE                        │
   │        "How many times PER YEAR do we expect it?"           │
   │        once a year = 1 · twice a year = 2                   │
   │        once every 10 years = 0.1 · every 4 years = 0.25     │
   ├─────────────────────────────────────────────────────────────┤
   │  ALE = ANNUALIZED LOSS EXPECTANCY  = SLE × ARO              │
   │        "How much do we expect to lose PER YEAR?"            │
   └─────────────────────────────────────────────────────────────┘
```

### Worked Example 1: Stolen Laptops 💻
- AV = $2,000 per laptop. A stolen laptop is a total loss → **EF = 100% (1.0)**
- **SLE** = $2,000 × 1.0 = **$2,000**
- The company loses about **5 laptops a year** → **ARO = 5**
- **ALE** = $2,000 × 5 = **$10,000 per year**

### Worked Example 2: Data Center Flood 🌊
- AV (data center equipment) = $1,000,000. A flood destroys about 40% → **EF = 0.4**
- **SLE** = $1,000,000 × 0.4 = **$400,000**
- Floods happen about **once every 10 years** → **ARO = 0.1**
- **ALE** = $400,000 × 0.1 = **$40,000 per year**

### Worked Example 3: Is a Control Worth Buying? 💰
A web server worth **$50,000** gets hit by an attack that destroys **60%** of its value (EF 0.6), **twice a year** (ARO 2).
- SLE = $50,000 × 0.6 = **$30,000**
- ALE (before) = $30,000 × 2 = **$60,000/year**

A WAF costing **$15,000/year** would reduce attacks to **once every 2 years** (ARO 0.5):
- ALE (after) = $30,000 × 0.5 = **$15,000/year**

```
   Value of the control = ALE(before) − ALE(after) − annual cost of control
                        = $60,000 − $15,000 − $15,000
                        = $30,000 per year saved  →  ✅ BUY IT
   (If the result is negative, the control costs more than the risk it removes.)
```

> 🧠 **Rule of thumb:** never spend more per year on a control than the yearly loss it prevents.

### Practice Problems ✍️
1. AV $80,000, EF 25%, ARO 3. SLE? ALE?
2. A risk has ALE $12,000 and SLE $48,000. What's the ARO?
3. A $200,000 asset, EF 50%, happens once every 5 years. ALE?

<details>
<summary><b>Show answers</b></summary>

1. SLE = 80,000 × 0.25 = **$20,000**. ALE = 20,000 × 3 = **$60,000**.
2. ARO = ALE ÷ SLE = 12,000 ÷ 48,000 = **0.25** (once every 4 years).
3. SLE = 200,000 × 0.5 = $100,000. ARO = 0.2. ALE = **$20,000**.

</details>

---

## 📖 Part 4 — The Risk Register 📋

A **risk register** is the central list of identified risks and how they're being handled.

## 🖼️ Figure 44.3 — A Risk Register with KRIs

| ID | Risk | Likelihood | Impact | Score | **Risk owner** | Strategy | **KRI** (key risk indicator) | **Threshold** | Status |
|---|---|---|---|---|---|---|---|---|---|
| R1 | Ransomware on file servers | 3 | 4 | 12 Critical | IT Director | Mitigate | % endpoints with EDR | < 98% = alert | EDR at 99% ✅ |
| R2 | Phishing compromise | 4 | 3 | 12 Critical | CISO | Mitigate | Phishing-sim click rate | > 5% = alert | 7% ⚠️ |
| R3 | Key vendor outage | 2 | 3 | 6 Medium | Procurement | Transfer | Vendor SLA uptime | < 99.9% | 99.95% ✅ |
| R4 | Unpatched critical vulns | 3 | 4 | 12 Critical | Ops Manager | Mitigate | Critical vulns > 14 days old | > 0 | 3 ⚠️ |

| Term | Meaning |
|---|---|
| **Risk owner** | The **person accountable** for managing a specific risk (not necessarily the one doing the work) |
| **Key risk indicator (KRI)** | A **metric** that warns that a risk is **increasing** (early-warning signal) |
| **Risk threshold** | The **level** at which a KRI or risk triggers action/escalation |

---

## 📖 Part 5 — Risk Appetite & Tolerance 🍽️

| Term | Meaning | Analogy |
|---|---|---|
| **Risk appetite** | The **amount and type** of risk an organization is **willing to pursue/accept** to achieve its goals: a **strategic** stance set by the board | How spicy you *like* your food |
| **Risk tolerance** | The **acceptable deviation** around the appetite: how much **variation** is OK for a specific risk before action is needed | How much extra spice you can *put up with* before you need water |

### Types of Risk Appetite (SY0-701)

| Appetite | Attitude | Example |
|---|---|---|
| **Expansionary** | **Willing to take more risk** for growth/innovation | A startup launching new products fast |
| **Conservative** | **Avoids risk**; prefers safety and stability | A bank or hospital |
| **Neutral** | **Balanced**: risks weighed case by case | A mature mid-size company |

---

## 📖 Part 6 — Risk Management Strategies (Responses) 🛡️

(From Chapter 22, now with the exam's sub-terms.)

| Strategy | Meaning | Example |
|---|---|---|
| **Mitigate** | Reduce likelihood or impact with **controls** | Install EDR, patch, add MFA |
| **Transfer** | Shift the **financial** impact to a third party | **Cyber insurance**, outsourcing with contractual liability |
| **Avoid** | **Stop** the risky activity | Don't store card numbers; retire a risky service |
| **Accept** | Consciously **live with** the risk (documented) | Low-impact risk where controls cost more than the loss |
| ↳ **Exception** | A **temporary, approved deviation** from a policy/standard for a specific case, usually with compensating controls and an expiry date | "Server X may run TLS 1.1 until the vendor update in June" |
| ↳ **Exemption** | Formal **release** from a requirement (often longer-term) | "The lab network is exempt from the EDR standard" |

> **Residual risk** = the risk **left over** after controls are applied. **Inherent risk** = the risk **before** any controls. Management must **accept** the residual risk.

```
   INHERENT RISK ──(apply controls: mitigate/transfer/avoid)──► RESIDUAL RISK ──► accept it
```

---

## 📖 Part 7 — Risk Reporting 📊

Communicating risk to the right people in the right form:
- **Board/executives:** top risks, trends, appetite vs actual exposure, KRIs breaching thresholds, investment needs (heat maps, dashboards).
- **Risk owners/managers:** detailed register entries, action plans, deadlines.
- **Regulators/auditors:** compliance-focused reports.
Good reporting is **regular, clear, honest and actionable**.

---

## 📖 Part 8 — Business Impact Analysis (BIA) ⏱️

A **BIA** identifies **critical business functions**, the systems they depend on, and **how much downtime and data loss** each can tolerate. It drives BC/DR planning (Chapter 32).

## 🖼️ Figure 44.4 — RPO and RTO on a Timeline ⭐

```
                 last good          DISASTER                     system back
                  backup            strikes                      online
   ──────────────────●────────────────💥───────────────────────────●──────────►  time
                     │◄──── RPO ─────►│◄─────────── RTO ─────────►│
                     │  data LOST     │   time to RESTORE service  │
                     │  (max allowed) │   (max allowed downtime)   │

   RPO (Recovery Point Objective): the MAXIMUM acceptable DATA LOSS, measured in time.
       RPO = 1 hour → you must back up/replicate at least every hour.
   RTO (Recovery Time Objective): the MAXIMUM acceptable DOWNTIME before service is restored.
       RTO = 4 hours → you need a recovery method (e.g., warm/hot site) that's that fast.
```

| Metric | Meaning | Drives |
|---|---|---|
| **RPO** | Maximum tolerable **data loss** (how far back you can go) | **Backup frequency**, replication |
| **RTO** | Maximum tolerable **downtime** | **Recovery strategy** (hot/warm/cold site, failover) |
| **MTTR**: Mean Time To Repair/Recover | **Average time to fix** a failed component/system | Lower = faster recovery |
| **MTBF**: Mean Time Between Failures | **Average time a system runs before failing** (for repairable systems) | Higher = more reliable |

### Reliability Math (bonus)

```
   Availability ≈ MTBF ÷ (MTBF + MTTR)

   Example: MTBF = 990 hours, MTTR = 10 hours
            Availability = 990 ÷ 1,000 = 0.99 = 99%

   To improve availability: INCREASE MTBF (more reliable parts, redundancy)
                            and/or DECREASE MTTR (spares on site, automation, skilled staff)
```

> You may also see **MTD/MTO** (Maximum Tolerable Downtime/Outage): the **absolute limit** before the business suffers irreparable harm. RTO must be **shorter** than MTD.

---

## 🧠 Memory Tricks

- **SLE = AV × EF. ALE = SLE × ARO.** "**S**ingle **L**oss = **A**sset × **E**xposure; **A**nnual **L**oss = **S**ingle × **R**ate."
- **ARO for "once every N years" = 1 ÷ N.**
- **Appetite = what you're hungry for. Tolerance = how much you can stomach.**
- **Expansionary = expand (more risk). Conservative = conserve (less risk). Neutral = middle.**
- **RPO = data (Point in time: how much data). RTO = Time (how long down).**
- **MTBF = Between failures (want BIG). MTTR = To Repair (want SMALL).**
- **Exception = temporary pass. Exemption = excused.**

---

## ⚠️ Exam Tip

- *"An asset is worth $100,000; an incident destroys 30% of it; it occurs twice a year. What's the ALE?"* → SLE $30,000 × 2 = **$60,000.**
- *"Which metric defines the maximum acceptable data loss?"* → **RPO.**
- *"Which metric defines how quickly a system must be restored?"* → **RTO.**
- *"Which metric measures reliability as average operating time between failures?"* → **MTBF.**
- *"A startup willing to take significant risks for rapid growth has which appetite?"* → **Expansionary.**
- *"A metric that signals a risk is rising, e.g., the number of unpatched systems."* → **Key risk indicator (KRI).**
- *"Management approves a temporary deviation from the patch policy for one server."* → **Exception** (risk acceptance).
- *"Which assessment type is performed after a merger is announced?"* → **Ad hoc.**
- **Math traps:** convert percentages to decimals (EF 30% = 0.3) and "once every N years" to 1 ÷ N before multiplying. **SLE is per event; ALE is per year.** Distractor answers are often the SLE when the question asked for the ALE (or vice versa), so re-read which one is asked.

---

## 🧪 Try It (25 minutes)

1. **Calculate your own ALE:** pick your phone. AV = its replacement cost. EF = 1.0 if stolen. ARO = how often you think it could be lost/stolen (e.g., 0.2 = once every 5 years). Is phone insurance cheaper than the ALE?
2. **Build a mini risk register** in a spreadsheet with 5 risks from your life or workplace: likelihood, impact, owner, strategy, one KRI and a threshold.
3. **Set your own RPO/RTO:** for your photos and schoolwork, how much could you afford to lose (RPO)? How long could you be without your laptop (RTO)? Does your current backup meet those numbers?

---

## ✅ Checkpoint Questions

1. Name the four risk assessment types by timing.
2. What's the difference between qualitative and quantitative analysis?
3. Write the formulas for SLE and ALE.
4. An asset worth $40,000 has EF 50% and ARO 4. What are the SLE and ALE?
5. What ARO represents "once every 20 years"?
6. What are a KRI, a risk owner and a risk threshold?
7. Explain risk appetite vs risk tolerance.
8. What's the difference between an exception and an exemption?
9. What's the difference between RPO and RTO?
10. A system has MTBF 495 hours and MTTR 5 hours. What's its approximate availability?

<details>
<summary><b>Show answers</b></summary>

1. **Ad hoc, recurring, one-time, continuous.**
2. **Qualitative** uses ratings/words (low/medium/high) based on judgment. **Quantitative** uses numbers and monetary values (SLE, ALE).
3. **SLE = AV × EF. ALE = SLE × ARO.**
4. SLE = 40,000 × 0.5 = **$20,000**. ALE = 20,000 × 4 = **$80,000**.
5. **0.05** (1 ÷ 20).
6. **KRI:** a metric warning that a risk is increasing. **Risk owner:** the person accountable for managing a risk. **Risk threshold:** the level that triggers action/escalation.
7. **Appetite** = how much risk the organization is **willing to pursue** overall (strategic). **Tolerance** = the **acceptable variation** around that for specific risks before action is required.
8. An **exception** is a **temporary, approved deviation** for a specific case. An **exemption** **releases** something from the requirement (often longer-term). Both are forms of risk acceptance.
9. **RPO** = maximum acceptable **data loss** (point in time to recover to). **RTO** = maximum acceptable **downtime** (time to restore).
10. 495 ÷ (495 + 5) = 495 ÷ 500 = **0.99 → 99%**.

</details>

---

## 📌 Chapter Summary

| Topic | Key points |
|---|---|
| Assessment timing | Ad hoc, recurring, one-time, continuous |
| Analysis | Qualitative (heat maps) vs quantitative (**SLE = AV × EF**, **ALE = SLE × ARO**) |
| Register | Risks, owners, KRIs, thresholds, strategies |
| Appetite & tolerance | Expansionary / conservative / neutral; tolerance = acceptable variation |
| Strategies | Mitigate, transfer, avoid, accept (exception, exemption); residual risk |
| Reporting | Right detail for board, owners, regulators |
| BIA | **RPO** (data loss), **RTO** (downtime), **MTTR** (repair time), **MTBF** (time between failures) |

**Next chapter →** *Chapter 45: Third-Party Risk Management.* Your risk register isn't complete until it includes everyone you depend on: vendors, suppliers and partners.
