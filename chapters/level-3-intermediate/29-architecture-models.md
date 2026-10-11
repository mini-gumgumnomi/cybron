# Chapter 29 — Architecture Models

**Level 3 · Can Score ~40%** · *Exam objective 3.1*

---

## 🎯 Goal

By the end of this chapter you will be able to compare the **security implications** of every architecture model in Security+:
- **Cloud** (responsibility matrix, hybrid considerations, third-party vendors)
- **Infrastructure as code (IaC)**, **serverless**, **microservices**
- **Network infrastructure** (physical isolation/air gap, logical segmentation, **SDN**)
- **On-premises**, **centralized vs decentralized**
- **Containerization**, **virtualization**
- **IoT**, **ICS/SCADA**, **RTOS**, **embedded systems**, **high availability**

You'll also learn the **considerations** used to compare them: availability, resilience, cost, responsiveness, scalability, ease of deployment, risk transference, ease of recovery, patch availability, inability to patch, power, compute.

---

## 🏠 Real-Life Story: Where Should the Restaurant Cook? 🍳

A restaurant owner has choices:
- **Own kitchen** (on-premises): full control, but you buy and fix everything yourself.
- **Rent a commercial kitchen** (IaaS): someone else maintains the building; you bring your own chefs and recipes.
- **Order from a catering company** (SaaS): you just serve the food.
- **One giant kitchen** (monolith) vs **many small food stalls**, each doing one dish (**microservices**).
- **Pop-up chefs** who appear only when an order arrives and vanish after (**serverless**).
- **A written recipe book** that any kitchen can follow to set itself up identically (**infrastructure as code**).

Each choice changes **who is responsible**, **what can go wrong**, and **how you protect it**.

---

## 📖 Part 1 — Cloud Architecture ☁️

### The Responsibility Matrix (Shared Responsibility Model)

## 🖼️ Figure 29.1 — Who Secures What?

| Layer | On-prem | IaaS | PaaS | SaaS |
|---|:---:|:---:|:---:|:---:|
| **Data & its classification** | 🟦 Customer | 🟦 Customer | 🟦 Customer | 🟦 Customer |
| **Identities & access (accounts, MFA)** | 🟦 | 🟦 | 🟦 | 🟦 |
| **Application** | 🟦 | 🟦 | 🟦 | 🟧 Provider |
| **Runtime / middleware** | 🟦 | 🟦 | 🟧 | 🟧 |
| **Operating system** | 🟦 | 🟦 | 🟧 | 🟧 |
| **Virtualization / hypervisor** | 🟦 | 🟧 | 🟧 | 🟧 |
| **Physical servers, network, storage** | 🟦 | 🟧 | 🟧 | 🟧 |
| **Physical data center** | 🟦 | 🟧 | 🟧 | 🟧 |

🟦 = customer responsibility · 🟧 = cloud provider responsibility

> 🔐 The provider secures the **cloud itself**; the customer secures **what's in the cloud**. **Data and identity are always the customer's job.** Most cloud breaches are **customer misconfigurations** (public storage, no MFA, leaked keys).

### Hybrid Considerations 🔗
A **hybrid cloud** mixes on-premises/private infrastructure with public cloud. Security challenges:
- **Consistent policies** across two very different environments (identity, logging, encryption).
- **Secure connectivity** between them (VPN, dedicated links).
- **Data movement**: where is data stored, and is it protected at each step?
- **Visibility**: one SIEM and one view across both.
- **Two sets of skills** needed by the team.

### Third-Party Vendors 🤝
Cloud setups rely on many vendors (the CSP, SaaS apps, managed security providers, marketplace tools). Each adds **supply-chain risk** (Chapter 23). Assess them, limit their access, and read the contract: SLAs, right to audit, breach notification (Chapter 45).

---

## 📖 Part 2 — Infrastructure as Code (IaC) 📜

**IaC** = defining servers, networks and settings in **code files** (e.g., Terraform, AWS CloudFormation, Ansible) instead of clicking around manually.

```
   # example IaC snippet (Terraform-style)
   resource "storage_bucket" "reports" {
     name          = "company-reports"
     public_access = false          ← security setting written in code
     encryption    = "AES256"
   }
```

| ✅ Security benefits | ⚠️ Risks |
|---|---|
| **Consistency**: every deployment identical, no "snowflake" servers | A mistake in the template is copied **everywhere** at once |
| Settings can be **reviewed and scanned** before deployment | **Secrets (passwords, keys) hard-coded** in code files and pushed to public repos |
| **Version control** shows who changed what, and allows rollback | Code repositories become high-value targets |
| Fast rebuild after an incident | |

---

## 📖 Part 3 — Serverless & Microservices ⚡

### Serverless (Function as a Service, FaaS)
You upload **small functions**; the cloud runs them **only when triggered** (e.g., AWS Lambda, Azure Functions). There's no server for you to manage.
- ✅ No OS to patch (the provider does it); scales automatically; you pay per use.
- ⚠️ Less visibility and control; each function needs **least-privilege permissions**; insecure code and **event injection** (malicious data in triggers); dependence on the provider.

### Microservices
An application built as **many small, independent services** that talk to each other through **APIs**, instead of one big **monolith**.

## 🖼️ Figure 29.2 — Monolith vs Microservices

```
   MONOLITH                                  MICROSERVICES
   ┌──────────────────────────┐              ┌────────┐  ┌────────┐  ┌────────┐
   │ login + catalog + cart + │              │ Login  │  │Catalog │  │  Cart  │
   │ payment + shipping       │              └───┬────┘  └───┬────┘  └───┬────┘
   │ (ONE big program)        │                  └─── APIs ──┼───────────┘
   └──────────────────────────┘                  ┌────────┐  ┌────────┐
                                                 │Payment │  │Shipping│
                                                 └────────┘  └────────┘
   ✘ one bug can crash everything             ✔ failures contained; scale parts separately
   ✔ fewer network connections                ✘ MANY APIs = bigger attack surface
                                              ✘ each service needs authentication between
                                                services, plus monitoring
```

---

## 📖 Part 4 — Network Infrastructure Models 🌐

### Physical Isolation (Air Gap) ✂️
An **air-gapped** network has **no physical or wireless connection** to other networks, especially the internet.
- Used for military systems, critical infrastructure, sensitive research.
- ✅ Very strong protection from remote attacks.
- ⚠️ Not perfect: **removable media** can bridge the gap (**Stuxnet**); updates are hard; insiders.

### Logical Segmentation 🧩
Separating traffic **using configuration**, not separate cables: **VLANs**, subnets, firewall rules, cloud security groups (Chapter 27). Cheaper and more flexible than physical isolation, but a misconfiguration can break the separation.

### SDN: Software-Defined Networking 🎛️
SDN **separates the "brain" of the network from the "muscle"**:

## 🖼️ Figure 29.3 — SDN Planes

```
   ┌──────────────────────────────────────────────────────────────────┐
   │ MANAGEMENT PLANE   admins configure & monitor (APIs, consoles)   │
   ├──────────────────────────────────────────────────────────────────┤
   │ CONTROL PLANE      the central CONTROLLER decides HOW traffic    │
   │                    should flow (routing decisions, policies)     │
   ├──────────────────────────────────────────────────────────────────┤
   │ DATA PLANE         switches/routers simply FORWARD packets       │
   │                    as instructed                                 │
   └──────────────────────────────────────────────────────────────────┘
```

- ✅ Central, programmable control; security policies applied everywhere instantly; easy segmentation.
- ⚠️ The **controller is a single high-value target**: compromise it and you control the whole network. Protect it heavily.

> These "planes" come back in **zero trust** (Chapter 33), which also has a **control plane** and a **data plane**.

---

## 📖 Part 5 — On-Premises, Centralized vs Decentralized 🏢

### On-Premises
Everything is in **your own building/data center**.
- ✅ Full control over hardware, data location and physical security.
- ⚠️ You pay for and do **everything**: power, cooling, patching, physical security, disaster recovery. Scaling is slow and expensive.

### Centralized vs Decentralized

| | **Centralized** | **Decentralized** |
|---|---|---|
| Meaning | Control and resources in **one place** (one data center, one identity system, one security team) | Spread across **many locations** / owners |
| ✅ Pros | Easier to manage, monitor and enforce consistent policy | No **single point of failure**; more resilient; local autonomy |
| ⚠️ Cons | **Single point of failure** / single big target | Harder to see everything; inconsistent security; more to manage |
| Example | One central SIEM, one Active Directory | Blockchain, branch offices each with their own IT |

---

## 📖 Part 6 — Virtualization & Containerization 📦

(Covered in Chapter 8. Here's the security view.)

| | **Virtualization (VMs)** | **Containerization** |
|---|---|---|
| Isolation | **Strong**: each VM has its own OS | **Weaker**: containers **share the host kernel** |
| Key risks | **VM escape**, VM sprawl, resource reuse, hypervisor flaws | Container escape, **vulnerable/malicious images**, too-privileged containers, secrets in images |
| Key defenses | Patch the hypervisor, strict VM inventory | Use **trusted, scanned images**, run as non-root, minimal base images, keep the host patched, orchestrator (Kubernetes) security |

---

## 📖 Part 7 — IoT, ICS/SCADA, RTOS & Embedded Systems 🏭

### IoT: Internet of Things 💡
Everyday objects with network connections: smart cameras, thermostats, TVs, speakers, medical wearables, smart locks.
- ⚠️ Typical problems: **default passwords**, rarely or never **patched**, weak encryption, insecure cloud apps, long lifetimes, and huge numbers of devices.
- ✅ Defenses: **separate IoT network segment**, change defaults, update firmware, buy from vendors with a security update policy.

### ICS / SCADA ⚙️
- **ICS (Industrial Control Systems):** systems that control **physical processes**: power plants, water treatment, factories, pipelines.
- **SCADA (Supervisory Control and Data Acquisition):** a type of ICS that monitors and controls equipment spread over **large areas** (a power grid, a pipeline).
- Components: **PLCs** (Programmable Logic Controllers, which control machines), **HMIs** (Human-Machine Interfaces, the operators' screens), sensors.

## 🖼️ Figure 29.4 — A Simple SCADA Network

```
   ┌──────────────── CORPORATE IT NETWORK ────────────────┐
   │  Office PCs · email · internet access                │
   └──────────────────────────┬───────────────────────────┘
                              │  FIREWALL / DMZ (strictly controlled; ideally one-way)
   ┌──────────────── OT / CONTROL NETWORK ────────────────┐
   │  SCADA server · HMI operator screens · historian     │
   └──────────────────────────┬───────────────────────────┘
                              │
   ┌──────────────── FIELD DEVICES ───────────────────────┐
   │  PLCs ── pumps · valves · turbines · conveyor belts  │
   └──────────────────────────────────────────────────────┘
   OT = Operational Technology. Priority order is often A-I-C:
   AVAILABILITY and SAFETY first (you can't just reboot a power plant to patch it).
```

- ⚠️ Problems: designed decades ago for **isolated** networks, so they use insecure protocols (e.g., Modbus, with no authentication). They're very hard to patch (can't stop production), and attacks can cause **physical damage or loss of life** (Stuxnet damaged centrifuges; attacks on Ukraine's power grid caused blackouts).
- ✅ Defenses: **strict segmentation** between IT and OT, air gaps where possible, monitoring OT traffic, strict access control, compensating controls when patching isn't possible.

### RTOS: Real-Time Operating System ⏱️
An OS that **must respond within guaranteed, very short time limits**: car braking systems, airbag controllers, pacemakers, industrial robots.
- ⚠️ Often minimal security features; **patching is difficult**; any delay or crash can be dangerous.
- ✅ Isolation, secure design, careful vendor updates.

### Embedded Systems 🔌
A computer **built into a device** to do **one dedicated job**: printers, ATMs, routers, smart TVs, car systems, medical devices.
- ⚠️ Limited CPU/memory (can't run normal antivirus), firmware rarely updated, sometimes **impossible to patch**.
- ✅ Network segmentation, firmware updates when available, disabling unneeded features.

---

## 📖 Part 8 — High Availability (HA) 🔁

**High availability** = designing systems to stay **up and running** with minimal downtime, often measured in "nines":

```
   99%      ("two nines")   ≈ 3.65 days  of downtime per year
   99.9%    ("three nines") ≈ 8.77 hours per year
   99.99%   ("four nines")  ≈ 52.6 minutes per year
   99.999%  ("five nines")  ≈ 5.26 minutes per year
```

Achieved with **redundancy** (no single point of failure), **load balancing**, **clustering**, **failover**, and **geographic dispersion** (Chapter 32).

---

## 📖 Part 9 — The Considerations ⚖️ (how to compare architectures)

| Consideration | Question to ask |
|---|---|
| **Availability** | Will it be up when needed? |
| **Resilience** | Can it **keep working** (perhaps degraded) when parts fail, and bounce back? |
| **Cost** | Up-front (CapEx) vs ongoing (OpEx)? Is security affordable? |
| **Responsiveness** | Is it fast enough for users? |
| **Scalability** | Can it grow or shrink with demand? |
| **Ease of deployment** | How fast and simple is it to set up (and set up **securely**)? |
| **Risk transference** | Can some risk be shifted (e.g., to the cloud provider via contract/SLA, or to insurance)? |
| **Ease of recovery** | How quickly can it be restored after failure or attack? |
| **Patch availability** | Does the vendor release security updates? |
| **Inability to patch** | Are there systems (ICS, embedded, medical) that **can't** be patched, so they need compensating controls? |
| **Power** | Does it need lots of power, or run on batteries (IoT)? Is backup power available? |
| **Compute** | Does it have enough processing power for security controls (encryption, agents)? |

## 🖼️ Figure 29.5 — Comparing Models at a Glance

| Model | Control | Patch burden | Typical big risk |
|---|---|---|---|
| On-premises | Highest | All yours | Cost, slow recovery |
| IaaS | High | OS and up | Misconfiguration |
| PaaS | Medium | App and data | Insecure code, IAM |
| SaaS | Low | Data and access | Weak access control, data sharing |
| Serverless | Low | Code only | Over-permissive functions |
| Containers | Medium | Images + host | Vulnerable images, shared kernel |
| IoT | Low | Often none | Default creds, no patches |
| ICS/SCADA | High (but fragile) | Very hard | Safety, legacy protocols |
| Embedded/RTOS | Low | Very hard | Inability to patch, limited compute |

---

## 🧠 Memory Tricks

- **"Data and identity are always yours."**
- **IaC = recipe book for infrastructure**: consistent, but a bad recipe spreads everywhere.
- **Serverless = pop-up chef. Microservices = food-court stalls. Monolith = one giant kitchen.**
- **SDN planes: Management (admin) → Control (brain) → Data (muscle).**
- **Air gap = no wire, no wireless.** USB sticks still cross it!
- **ICS/SCADA priorities: safety and availability first.**
- **RTOS = Real-Time = no delays allowed.**

---

## ⚠️ Exam Tip

- *"In a PaaS model, who patches the operating system?"* → **The provider.**
- *"Which architecture lets a template mistake be replicated across hundreds of servers?"* → **IaC.**
- *"An attacker compromising the SDN controller could…"* → **control the entire network** (protect the **control plane**).
- *"A water-treatment plant controller can't be patched."* → **ICS/SCADA**, inability to patch. Use **segmentation/isolation** as compensating controls.
- *"Which model has no servers for the customer to manage, with code running only when triggered?"* → **Serverless.**
- *"Which design has a single point of failure but easier management?"* → **Centralized.**
- *"Which isolation method uses no network connection at all?"* → **Air gap** (physical isolation).

---

## 🧪 Try It (25 minutes)

1. **Explore a shared responsibility page:** search "AWS shared responsibility model" or "Microsoft shared responsibility." Compare it to Figure 29.1.
2. **Find IoT in your home:** list every connected device (TV, speaker, camera, doorbell, router, printer). For each: Has the default password been changed? When was the firmware last updated? Could it go on a separate guest network?
3. **Read about an ICS attack:** search "Ukraine power grid cyberattack 2015" and note how the attackers moved from IT into OT.
4. **Calculate uptime:** what does 99.95% availability allow per year? (Answer below.)

> Answer to 4: 0.05% of 8,760 hours ≈ **4.38 hours** of downtime per year.

---

## ✅ Checkpoint Questions

1. In SaaS, which two things remain the customer's responsibility?
2. Give one security benefit and one risk of infrastructure as code.
3. Why do microservices increase the attack surface?
4. What are the three SDN planes, and which is the most valuable target?
5. Can an air-gapped network be infected? How?
6. What's the main security difference between VMs and containers?
7. Why are ICS/SCADA systems hard to secure?
8. What makes an RTOS different from a normal OS?
9. Name four "considerations" used to compare architecture models.
10. What does "inability to patch" mean, and what should you do about it?

<details>
<summary><b>Show answers</b></summary>

1. **Data** (classification, protection) and **identity/access management** (accounts, permissions, MFA).
2. Benefit: **consistency, reviewable/version-controlled settings, fast rebuilds**. Risk: **one template error spreads everywhere**, or **secrets hard-coded** in code.
3. There are **many services communicating through APIs**, and each API and connection is a potential entry point that needs authentication and monitoring.
4. **Management, control, data.** The **control plane** (the SDN controller) is the most valuable target.
5. **Yes**, via **removable media**, malicious insiders, or infected maintenance laptops (e.g., Stuxnet).
6. **VMs** each have their own OS (strong isolation). **Containers share the host kernel** (weaker isolation).
7. Old insecure protocols, **availability/safety requirements** that make patching and reboots hard, long lifetimes, and attacks can cause **physical harm**.
8. It must respond within **strict, guaranteed time limits** (deterministic timing).
9. Any four of: availability, resilience, cost, responsiveness, scalability, ease of deployment, risk transference, ease of recovery, patch availability, inability to patch, power, compute.
10. Some systems **can't receive security updates** (vendor support ended, or they can't be taken offline). Use **compensating controls**: isolation/segmentation, monitoring, strict access control.

</details>

---

## 📌 Chapter Summary

| Model | Key security point |
|---|---|
| Cloud | Shared responsibility; data and identity are always the customer's |
| Hybrid | Consistent policy, secure links, visibility across environments |
| IaC | Consistent and reviewable; protect secrets and templates |
| Serverless | Provider patches; least-privilege functions |
| Microservices | Contained failures; many APIs to secure |
| Air gap / segmentation / SDN | Physical vs logical separation; protect the SDN controller |
| On-prem / centralized / decentralized | Control vs cost; single point of failure vs complexity |
| VMs / containers | Strong vs shared-kernel isolation |
| IoT / ICS / RTOS / embedded | Hard or impossible to patch → segment and monitor |
| High availability | Redundancy; measured in "nines" |

**Next chapter →** *Chapter 30: Securing Enterprise Infrastructure.* Let's build an actual secure network: zones, firewalls, 802.1X, VPNs and SASE.
