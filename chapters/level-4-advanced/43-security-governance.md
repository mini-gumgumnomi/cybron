# Chapter 43 — Security Governance

**Level 4 · Advanced Knowledge** · *Exam objective 5.1*

---

## 🎯 Goal

By the end of this chapter you will be able to summarize the elements of effective security governance:
- **Guidelines, policies** (AUP, information security, business continuity, disaster recovery, incident response, SDLC, change management), **standards** (password, access control, physical security, encryption), **procedures** (change management, onboarding/offboarding, playbooks)
- **External considerations:** regulatory, legal, industry, local/regional, national, global
- **Monitoring and revision**
- **Governance structures:** boards, committees, government entities, centralized/decentralized
- **Roles and responsibilities for systems and data:** owners, controllers, processors, custodians/stewards

---

## 🏠 Real-Life Story: Running a Football Club ⚽

A professional football club has:
- A **board of directors** that sets the club's direction and budget.
- **Committees** (finance, safety, youth academy) that oversee specific areas.
- The **league and government** setting rules every club must follow.
- **Club policies** ("respect referees"), **standards** (kit colours, pitch size), **procedures** (matchday safety checklist) and **guidelines** (training tips).
- Clear **roles**: the owner, the manager, the groundskeeper who looks after the pitch.

**Governance** = **how an organization is directed and controlled**: who decides, what rules exist, who is accountable, and how compliance is checked.

---

## 📖 Part 1 — The Governance Documents (Deeper Look) 📚

Recall Chapter 22's pyramid: **policy → standard → procedure**, with **guidelines** as optional advice.

## 🖼️ Figure 43.1 — The Documents in SY0-701

```
   ┌────────────────────────────────────────────────────────────────────────────┐
   │ POLICIES (mandatory, high-level "what & why", approved by senior mgmt)     │
   │  AUP · Information security · Business continuity · Disaster recovery ·    │
   │  Incident response · SDLC · Change management                              │
   ├────────────────────────────────────────────────────────────────────────────┤
   │ STANDARDS (mandatory, specific "which/how much")                           │
   │  Password · Access control · Physical security · Encryption                │
   ├────────────────────────────────────────────────────────────────────────────┤
   │ PROCEDURES (mandatory, step-by-step "how")                                 │
   │  Change management · Onboarding/offboarding · Playbooks                    │
   ├────────────────────────────────────────────────────────────────────────────┤
   │ GUIDELINES (optional, recommended best practice)                           │
   └────────────────────────────────────────────────────────────────────────────┘
```

### Policies

| Policy | Purpose | Key contents |
|---|---|---|
| **AUP** (Acceptable Use Policy) | What users may/may not do with company IT | Personal use, prohibited activities, monitoring notice, consequences; users **acknowledge** it |
| **Information security policy** | The **top-level** security policy: goals, scope, responsibilities, authority of the security team | Often the "parent" of other policies |
| **Business continuity (BC)** | Keep **critical business functions** running during disruptions | BIA results, priorities, alternate processes, communication |
| **Disaster recovery (DR)** | **Restore IT systems and data** after a disaster | Recovery sites, backup strategy, RTO/RPO, recovery order |
| **Incident response (IR)** | How security incidents are handled | Definitions, severity levels, IR team, reporting, the IR process (Chapter 41) |
| **SDLC** (Software Development Life Cycle) | Building software **securely** | Secure coding standards, code review, security testing (SAST/DAST), separation of environments (dev/test/prod) |
| **Change management** | How changes are requested, approved and documented | CAB, backout plans, emergency changes (Chapter 33) |

### Standards

| Standard | Example requirements |
|---|---|
| **Password** | Minimum 14 characters, MFA for remote access, no reuse of last 24 passwords, lockout after 10 failures |
| **Access control** | RBAC, least privilege, quarterly access reviews, disable accounts within 24 h of departure |
| **Physical security** | Badge + PIN for server rooms, visitors escorted, CCTV retention 90 days |
| **Encryption** | AES-256 for data at rest, TLS 1.2+ in transit, keys in HSM/KMS, RSA ≥ 2048 |

### Procedures

| Procedure | Example |
|---|---|
| **Change management** | The steps to submit, test, approve and implement a change |
| **Onboarding** | Identity proofing, account creation, training, signing the AUP and NDA, issuing equipment |
| **Offboarding** | Disable accounts, revoke access and certificates, collect devices and badges, exit interview, transfer data ownership |
| **Playbooks** | Step-by-step response guides for specific incidents (phishing, ransomware, lost laptop) |

### Monitoring and Revision 🔁
Governance documents are **living documents**:
- **Review regularly** (e.g., annually) and **after major events**: incidents, new laws, new technology, mergers, audit findings.
- **Monitor compliance** with policies (audits, automated checks, metrics).
- Keep **version control** and approval records.

---

## 📖 Part 2 — External Considerations 🌍

Security programs must follow rules **outside** the organization, at every level:

| Consideration | Meaning | Examples |
|---|---|---|
| **Regulatory** | Rules from **regulators** (government agencies) for specific sectors | Financial regulators, health regulators, data protection authorities |
| **Legal** | **Laws** and contractual obligations; lawsuits | Breach notification laws, computer misuse laws, contracts with customers |
| **Industry** | **Industry standards and requirements**, often enforced by contract | **PCI DSS** (card payments), NERC CIP (US power utilities) |
| **Local / regional** | City, state or regional laws | US state privacy laws (e.g., California's CCPA/CPRA), state breach-notification laws |
| **National** | Country-wide laws | HIPAA, SOX, GLBA (USA); national data protection laws (e.g., India's DPDP Act 2023) |
| **Global** | Laws/standards that apply across borders | **GDPR** (applies worldwide to anyone processing EU residents' data), ISO/IEC 27001 |

> 💡 A multinational company may face **all** of these at once, and they can conflict. That's why legal and compliance teams are part of security governance.

---

## 📖 Part 3 — Governance Structures 🏛️

| Structure | Role |
|---|---|
| **Boards** (board of directors) | **Ultimate accountability**. Set strategy and risk appetite, approve major policies and budgets, receive security reports |
| **Committees** | Focused groups overseeing specific areas: **audit committee**, **risk committee**, **security steering committee**, Change Advisory Board |
| **Government entities** | Public agencies that are **governed** by laws and oversight bodies, or that **regulate** others (e.g., CISA guidance, data protection authorities) |
| **Centralized governance** | **One central team** sets and enforces security for the whole organization: consistent, efficient, but can be slow and distant from local needs |
| **Decentralized governance** | **Business units or regions** manage their own security within broad rules: flexible and local, but risk of **inconsistency** and gaps |

## 🖼️ Figure 43.2 — Centralized vs Decentralized

```
   CENTRALIZED                                  DECENTRALIZED
         ┌──────────────┐                       ┌────────┐  ┌────────┐  ┌────────┐
         │ Central CISO │                       │ EU unit│  │US unit │  │Asia    │
         │ + security   │                       │security│  │security│  │security│
         │ team         │                       └────────┘  └────────┘  └────────┘
         └──────┬───────┘                        each sets its own rules within
      ┌─────────┼─────────┐                      broad group-level guidance
      ▼         ▼         ▼
    EU unit   US unit   Asia unit
   ✔ consistent, economies of scale            ✔ fast, local knowledge
   ✘ slower, less local flexibility             ✘ inconsistent controls, duplicated effort
```

> Many organizations use a **hybrid**: central policy and standards, local implementation.

---

## 📖 Part 4 — Roles & Responsibilities for Systems and Data ⭐

## 🖼️ Figure 43.3 — Who Does What With Data?

```
   ┌─────────────────────────────────────────────────────────────────────────────┐
   │ DATA OWNER (senior business leader, e.g. Head of HR)                        │
   │  ACCOUNTABLE for the data: decides classification, who gets access,         │
   │  retention. "It's my data; I answer for it."                                │
   └───────────────────────┬─────────────────────────────────────────────────────┘
                           │ delegates day-to-day care to
   ┌───────────────────────▼─────────────────────────────────────────────────────┐
   │ DATA CUSTODIAN / STEWARD                                                    │
   │  Custodian (usually IT): implements controls: backups, encryption,          │
   │  permissions, storage                                                       │
   │  Steward (business side): data quality, correct use, metadata, meaning      │
   └─────────────────────────────────────────────────────────────────────────────┘

   PRIVACY LAW ROLES (e.g., GDPR):
   DATA CONTROLLER  decides WHY and HOW personal data is processed (e.g., the employer)
   DATA PROCESSOR   processes personal data ON BEHALF OF the controller
                    (e.g., the outsourced payroll company, a cloud provider)
   DATA SUBJECT     the PERSON the data is about (the employee)
```

| Role | Responsibility | Example |
|---|---|---|
| **Owner** | **Accountable** for a system or data set; classifies it, approves access, sets retention | VP of Sales owns the CRM data |
| **Controller** | (Privacy) **Determines the purposes and means** of processing personal data; legally responsible | A hospital deciding how patient data is used |
| **Processor** | (Privacy) **Processes data on behalf of** the controller, following its instructions | A cloud email provider, a payroll company |
| **Custodian / steward** | **Day-to-day management**: custodians apply technical controls (backups, access, encryption); stewards ensure data quality and proper use | IT team backing up the CRM; a data steward cleaning records |

> ⚠️ **Accountability stays with the owner/controller.** A controller that outsources to a processor is **still responsible** for protecting the data (just like risk transfer in Chapter 22).

---

## 🧠 Memory Tricks

- **Policy = WHAT/WHY, Standard = WHICH, Procedure = HOW, Guideline = SHOULD.**
- **7 policies: "A Info BC DR IR SDLC CM"**: think "**A**ll **I**nformation **B**ecomes **D**ata **I**n **S**oftware **C**hanges."
- **External layers: Local → Regional → National → Global**, plus Regulatory, Legal, Industry.
- **Owner = accountable. Custodian = hands-on caretaker. Controller = decides why/how. Processor = does it for them.**
- **Board = the captain. Committees = the officers. CAB = the change gatekeepers.**

---

## ⚠️ Exam Tip

- *"Which document defines the steps for revoking a departing employee's access?"* → **Offboarding procedure.**
- *"Who is accountable for classifying a data set?"* → **Data owner.**
- *"A payroll company processes employee data on behalf of a retailer. The payroll company is the…"* → **Processor** (the retailer is the **controller**).
- *"IT performs daily backups and manages permissions for HR data."* → **Custodian.**
- *"Which policy covers secure coding and testing requirements?"* → **SDLC policy.**
- *"A company with many subsidiaries lets each manage its own security."* → **Decentralized** governance.
- *"Policies should be reviewed after a major incident or new regulation."* → **Monitoring and revision.**

---

## 🧪 Try It (25 minutes)

1. **Read a real security policy template:** search "SANS security policy templates" (free). Open the Acceptable Use Policy and the Password Construction Guidelines. Is the password document a *policy*, *standard* or *guideline*?
2. **Map your external considerations:** for a pretend online shop in your country selling to EU customers and taking card payments, list every external requirement (national law, GDPR, PCI DSS…).
3. **Identify roles:** for your school or workplace email system, who is the owner? The custodian? Is there a processor (e.g., Google/Microsoft)?

---

## ✅ Checkpoint Questions

1. Name the seven policies listed in SY0-701.
2. Name the four standards listed in SY0-701.
3. Name the three procedures listed in SY0-701.
4. What's the difference between business continuity and disaster recovery?
5. Give an example of each external consideration: industry, national, global.
6. Why must governance documents be monitored and revised?
7. Compare centralized and decentralized governance.
8. What's the difference between a data owner and a data custodian?
9. What's the difference between a data controller and a data processor?
10. What role does a board of directors play in security?

<details>
<summary><b>Show answers</b></summary>

1. **AUP, information security, business continuity, disaster recovery, incident response, SDLC, change management.**
2. **Password, access control, physical security, encryption.**
3. **Change management, onboarding/offboarding, playbooks.**
4. **BC** keeps **critical business functions** running during a disruption. **DR** **restores IT systems and data** after a disaster.
5. Industry: **PCI DSS**. National: e.g., **HIPAA/SOX** (US) or a national data protection act. Global: **GDPR** / ISO 27001.
6. Threats, technology, laws and the business **change**; outdated documents leave gaps and may break new regulations.
7. **Centralized:** one team sets and enforces security (consistent, efficient, less flexible). **Decentralized:** units manage their own (flexible and local, but risk of inconsistency).
8. The **owner** is **accountable** (classifies, approves access). The **custodian** **implements and maintains** the controls day to day (backups, permissions).
9. The **controller decides why and how** personal data is processed. The **processor processes it on the controller's behalf**.
10. **Ultimate accountability**: sets strategy and risk appetite, approves major policies and budgets, and oversees security through reports and committees.

</details>

---

## 📌 Chapter Summary

| Element | Key points |
|---|---|
| Policies | AUP, infosec, BC, DR, IR, SDLC, change management |
| Standards | Password, access control, physical security, encryption |
| Procedures | Change management, onboarding/offboarding, playbooks |
| Guidelines | Optional recommendations |
| External | Regulatory, legal, industry, local/regional, national, global |
| Monitoring & revision | Regular and event-driven reviews |
| Structures | Boards, committees, government entities, centralized vs decentralized |
| Roles | Owner (accountable), controller (decides), processor (on behalf), custodian/steward (day-to-day) |

**Next chapter →** *Chapter 44: Risk Management (with the Math).* The board needs numbers. Let's calculate SLE, ALE and ARO, and measure recovery with RTO, RPO, MTTR and MTBF.
