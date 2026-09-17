# soma-moa : Design Philosophy & Prior Art Declaration
> **original design:** `deundeuni (soma-moa)` | **repository:** `github.com/soma-moa`  
> **initial record date:** 2026-08-24 | **prior art declaration:** 2026-08-25 | **v2.2.1 Revision:** 2026-09-17  
> **domain:** `somamoa.ai.kr` | **License:** CC BY 4.0 & DPL  
> **Naming Definition:** The open-source protocol and codebase are denoted as `soma-moa` (lowercase with a hyphen), while the service brand and representative project name are `Somamoa`, sharing the same identity.  
> **Original Clause:** The Korean text (`PHILOSOPHY.ko.md`) is the definitive original version; translations are for reference purposes only.

This document is a record of *why* `soma-moa` was designed this way.  
It is not merely about results, but the process; not just specifications, but the traces of reasoning.

---

### 0. Designed Beginning with the Mother Tongue

soma-moa is not a technology conceived in English and then translated into Korean.  
It originally began from the knowledge accumulated in daily life—handling various machines and performing sample work in factories, and working as a construction worker. It started as a record sparked by a recent encounter with AI, thinking, "Couldn't I make materials out of this, too?"

It is a protocol reasoned deeply in Korean and proven through global standard code.  
Therefore, `moa` is not a nickname, but its true name.

While the English words 'gather' or 'collect' translate the basic meaning, the specific warmth of "embracing and bringing together fragmented error logs and distributed terminals into one" is captured only in the Korean word 'moa'.

This is the identity of soma-moa and the starting point of its design.

**Modesty & Non-Exclusivity Notice:**  
This protocol was conceived from the daily life and field experience of a single designer. However, it does not exclude the possibility that similar technical ideas or concepts may have been independently researched by other researchers prior to this. This document is published open and free of charge as public Prior Art, aiming to prevent exclusive monopolization by specific entities and to allow anyone to freely reference and develop it.

---

### 1. v0.1 OSRP - When It Was Just a Skeleton

**Project Name: OSRP (Open Symbiotic Routine Protocol)**

Initially, we established the basic framework.
- **Zero Trust Security:** Aims to allow connections only through the authorized network, directing sensor data straight to the internal network.
- **3-Stage Escalation:** WebRTC Video -> Telemetry Log -> Human direct dispatch.
- **Human Ultimate Control:** Controls situations where the robot makes autonomous decisions and guarantees the right of human intervention.

The word 'Routine' was discarded because it made it look like a simple scheduler, reflecting that it lacked intuitiveness as an engineering abbreviation.

---

### 2. v1.0 SOMA - Putting on a Body

**Project Name: SOMA (Symbiotic Operations & Machine Architecture)**

We scaled up the governance needed the moment a virtual AI puts on a physical body (Greek: Soma).

- **Design Structure:** Separated into a governance layer at the top responsible for safety and control, regardless of the hardware chassis form (wheels, quadruped, humanoid).
- **Enactment of Axiom 0:**  
  *"The Robot/AI is Sub, the system governance is Main, but even that governance is Auxiliary to the human's main task."*

---

### 3. v1.5 Naming Exploration - The Standard After 20 Names

Besides the English name SOMA, we reviewed over 20 names seeking one that was easy to pronounce and intuitive.

- **Bodeum, Gyeol, Irum** — The pronunciation felt somewhat heavy.
- **Nuri, Miso, Uri** — The technical identity was not clearly conveyed.
- **Gori, Dari, Sai** — The scope felt too limited to encompass an entire platform gathering N:1.

**Three Established Criteria:**
1. Must be pronounceable in 0.1 seconds.
2. The operational structure should be imaginable upon hearing it.
3. Must convey the scalability of gathering distributed terminals into one.

---

### 4. v2.0 soma-moa - Completion of Name and Notation

**Official Name: soma-moa by deundeuni**

- **moa:** The essence of gathering scattered error logs and standards into one place.
- **Linguistic Symmetry:** The visual and auditory rhyme match of S O M A (ㅗㅏ) and m o a (ㅗㅏ) in Korean vowels.
- **Lowercase Confirmation:** Finalized as `soma-moa` in lowercase with a hyphen for the identity of an open-source protocol that developers can comfortably call and use in codebases.

---

### 4-1. v2.2 Final - 4-Tier Survival Architecture and L2 FSM Specification

Building on the v2.0 name, the basic skeleton of the system was finalized in v2.2.

- **L0 Physical:** CWP Battery-Swap + V-Home Self-Align + 0.1ms Hardware Intercept E-Stop (Aims for Motor EN PIN LOW block control)
- **L1 Compute:** Chiplet-APU Many as One Dual-Redundant + CCS 70%/100ms Raft Role-Swapping + 3-Tier Shoulder Surveillance
- **L2 Governance:** Physical separation of Brain (Probabilistic) vs. Governance (Deterministic) + eFPGA 0.1ms Blocker + FSM
- **L3 Social:** Quiet Assist Haptic 1x/2x + Anonymized Delta Logging PII destruction within 10 seconds

**Edge Verification Parameters (Target Design Benchmarks):** CBOR L0 24B + L1 33B <50B, SDK 35.2KB <42KB, RAM 3.2KB <10MB, L0 Sync 0.1ms HMAC HW Bypass / L1 Async 2~5ms Ed25519

**L2 FSM Transition Conditions and Role Definitions:**
- **IDLE:** Normal standby state.
- **MONITOR:** Real-time monitoring of edge sensors and logs.
- **VALIDATE (<0.02ms):** Deterministic safety rule verification based on eFPGA.
- **PRELOCK (80%):** Preemptive hardware lock preparation upon reaching 80% risk prediction probability.
- **OVERRIDE:** The stage where abnormal control attempts by the AI inference (Brain) are physically and immediately nullified by L2 deterministic governance and human control rights, securing dominance.
- **E_STOP_LATCH (<0.1ms):** Secures the motor power cutoff latch within 0.1ms.
- **RECOVERY:** Recovery is not permitted without Ed25519 human signature approval, maintaining a permanent latch state.

---

### 4-2. v2.2 Expansion - From Daily Life to the Field

- **3 Types of AS (After-Sales):** Remote/OTA, Dispatch, Resident (Hospital/Factory/Department Store/Logistics/Repair Center/Food Court).
- **Personal Customization:** Medication/To-do/Health Routines, Device Repair History/Warranty, Diet/Allergies.
- **Exploratory Search:** Library Librarian (searching for books by cover/feeling/plot) + Music Search (searching by humming/feeling/lyrics).

---

### 4-3. v2.2 Sub-classification - Gathering into Enterprise/Daily/Personal

`moa` gathers everything, but its uses must be divided to remain lightweight. Therefore, it was sub-classified into three categories.

- **Enterprise:** Operating environments where operational continuity is critical. Resident in factories, logistics, hospitals, and AS centers. Aims for L0 0.1ms block control + L1 Many as One + L2 deterministic execution focus. Guarantees final human judgment.
- **Daily:** Environments requiring exploration and support. Food courts, department store service centers, libraries, music. Focuses on Vibe Search + L3 escalation. Avoids assertive guessing when confidence is below 90%.
- **Personal:** Environments respecting personal domains. Medication/To-do/Health, Diet/Allergies, Repair History. Aims for PII destruction within 10s + Haptic 1x/2x + Minimizing indiscriminate recording.

Connecting everything while distributing the burden is the principle of being `Auxiliary`.

---

### 4-4. Inheritance of Safety Philosophy - Heinrich Only as a Basic Philosophy

Heinrich's 300:29:1 is a philosophical foundation established in 1931. Rather than limiting the ratio itself to an absolute numerical value, it is cited as the motivation for *why* preventive measures must be gathered.

The actual implementation is applied expansively based on modern safety frameworks:
- **Safety-II / Resilience (Hollnagel):** Focuses not only on preventing accidents but on stably maintaining the 9,999 normal operating states. Implemented with Many as One and Raft-based architectures.
- **Just Culture + Anonymous Reporting:** Applies CBOR 24B anonymous logging + PII 10-second destruction + a system minimizing the recording of minor items to foster an autonomous reporting culture.
- **Active Swiss Cheese Model:** Aims to proactively mitigate defects by actively detecting defense line leakage risks through Leukocyte Scanning, T-Reg 15%, and Tri-State isolation.
- **Establishing Quantitative Standards:** Cites formal standard indicators such as ISO 13849-1 Cat 4 PL e / IEC 61508 SIL3 / GDPR 5(1)(e) instead of the Heinrich ratio.

> [S-01] Heinrich 1931 is cited as a historical and philosophical motivation, while the actual implementation is based on Safety-II, Just Culture, deterministic control, and an anonymous near-miss reporting system.

---

### 4-5. Organic Integration and Self-Preemptive Action Philosophy

Aims for a structure where preemptive actions are completed through organic integration within the field itself.

- At L0, V-Home precisely absorbs physical errors within a ±5mm range.
- At L1, aims to resolve issues within the fabric through 70% Raft re-election, 85% backpressure, and leukocyte isolation.
- At L2, eFPGA executes lock control with <0.02ms VALIDATE and records internal logs.

Only in situations where self-resolution is difficult, L3 performs human administrator connection via WebRTC after 1x/2x haptic notifications, protecting the dignity of technicians by leaving the final judgment to humans.

---

### 4-6. Quantitative Core Specification (System Specification Summary)

The comprehensive specification of key quantitative parameters by layer (Target Design Benchmarks) for comparison with prior art and examination alignment is as follows.

- **L0 Physical Latency —** Aims for 0.1ms Hardware Intercept E-Stop block control (Motor EN PIN LOW).
- **L0 Physical Error Absorption —** V-Home Self-Align ±5mm precision absorption.
- **L0/L1 Verification Latency —** L0 Sync 0.1ms HMAC HW Bypass / L1 Async 2~5ms Ed25519.
- **L1 Compute Consensus Threshold —** CCS Raft 70% agreement / 100ms Role-Swapping.
- **L1 Compute Backpressure —** Automatic throttling upon detecting 85% backpressure inside the fabric.
- **L1 Compute Data Payload —** CBOR packet L0 24B + L1 33B (Limited to <50B).
- **L2 Governance Verification Latency —** eFPGA deterministic VALIDATE <0.02ms.
- **L2 Governance Prediction Threshold —** PRELOCK preemptive block preparation upon reaching 80% risk probability.
- **L2 Governance Self-Healing Constraint —** T-Reg 15% limit and permanent isolation upon 3 consecutive failures.
- **L3 Social Confidence Threshold —** No guessing if Daily Vibe Search confidence is below 90%.
- **L3 Social PII Destruction Cycle —** Anonymized Delta Logging destroyed within 10 seconds.
- **Edge Embedded Resource Constraints —** SDK size 35.2KB (<42KB), RAM 3.2KB (<10MB).

---

### 5. Auxiliary Governance & Prior Art Declaration

**Purpose of Publication (2026-08-25):** This document aims to publish the minimum safety auxiliary specifications for the coexistence of AI, robots, and humans as prior art. This is to mitigate the risk of exclusive patent monopolization by specific entities and to establish it as public technology accessible to anyone.

- **Premise of Coexistence:** "Smile on the way to work, smile on the way home."
- **Principle of Auxiliary:** Governance performs a lightweight auxiliary role that does not interfere with main tasks.
- **Deterministic Control:** Aims for power bus block control via the L0 breaker even when abnormal AI behavior is detected.

---

### 5-1. Technician Dignity & Quiet Assist Protocol

- **Quiet Assist:** Utilizes 1x/2x haptic notifications recognizable only to the worker themselves, instead of excessive alarm sounds.
- **Consideration Without Records:** Eases the burden by automatically deleting minor simple mistakes after 10 seconds, while retaining records for physical risk items.
- **Principle of Treating Technicians:** Establishes value as an Auxiliary, not for surveillance purposes.

**Summary:** Physical safety is clearly secured through L0 block control, while social safety is softly implemented through vibration notifications and autonomous deletion clauses.

---

### 5-2. Self-Healing Reset Philosophy - Soft vs. Hard

- **Soft Reset (Autonomous control, human signature not required):** L0/L1 self-healing — Chiplet restart, Raft re-election, Token Bucket reset, V-Home re-docking. Performed autonomously under the conditions of a T-Reg 15% limit and permanent isolation upon 3 consecutive failures.
- **Hard Reset (Human confirmation required):** L2 E_STOP_LATCH release. After releasing the Motor EN LOW latch, the RECOVERY stage strictly requires Ed25519-based human signature approval. Avoids automatic restart and complies with ISO 13849-1 / IEC 61508 standards.

---

### 6. Technical Drafting Support & Legal Doctrine

- **Technical & Legal Drafting Support:** Generic Generative AI Text Refinement & Structuring Tools.
- **Notice on Role and IP Ownership:** This document utilized generic generative AI text refinement and structuring tools to assist in structuring technical context, reviewing, and refining expressions. This notice is for role transparency; AI prompts and internal reasoning processes are not disclosed. All core technical Conception, independent system architecture design, final decisions, and Intellectual Property (IP) ownership belong entirely to the original creator (deundeuni / soma-moa).
- **Legal Invocation (USPTO / EPO / Case Law):** Invokes the US Supreme Court / CAFC precedent (*Thaler v. Vidal*) denying AI inventorship, the USPTO AI Inventorship Guidance (2024.02), and EPO Examination Guidelines (G-II 3.3.1). Generic AI tools are merely auxiliary means for refining technical documents; it is legally established that the independent conception subject of this technical system is the human designer (deundeuni).
- **Standard Compliance:** Aims for compliance with ISO 13849-1 Cat 4 / PL e, IEC 61508 SIL3, and GDPR 5(1)(e) standards.

---

### 7. Defensive Rights & Somamoa Brand Expansion

- **Open-source protocol codename:** `soma-moa`
- **Official project and brand name:** `Somamoa`
- **Official domains:** `somamoa.ai.kr` / `Somamoa.ai.kr`
- **Defensive Rights & Publication:** The technical configuration and ideas of this protocol are disclosed free of charge as prior art. It aims to protect the technology ecosystem by expanding the scope of the public domain against unauthorized patenting by other entities.

---

### 8. Open Foundation Models, Sole Design, and Attribution (Conception)

This protocol originated from the reasoning of a single designer (deundeuni). It began from actual, everyday knowledge accumulated while handling machines and performing sample work in a factory, and participating in the field as a construction worker.

soma-moa is a prior art record that systematized this field reasoning into a global standard code.

During this design systematization process, generic AI context refinement tools, alongside transformer architectures and open technical foundations, were utilized as auxiliary review tools. The legal and technical subject of all core conception and independent architecture design lies with deundeuni.

---

### 9. Sources and Prior Art Basis

- **Safety Theory:** Heinrich (1931) 300/29/1 — Philosophical motivation, Reason (1990) Swiss Cheese, Hollnagel Safety-II/Resilience, Defense in Depth, Fail-Safe, ALARP, Just Culture.
- **Functional Safety:** ISO 13849-1:2023 PL e, IEC 61508 SIL3, GDPR Article 5(1)(e).
- **Communication/Consensus:** RFC 8949 CBOR, Ongaro 2014 Raft, HMAC-SHA256, Ed25519 RFC8032.
- **Legal:** USPTO AI Inventorship Guidance 2024.02, Thaler v. Vidal 2022, EPO G-II 3.3.1.
- **Verification and Drafting Tools:** Generic Generative AI Text Refinement & Structuring Tools (Conception by deundeuni).
- **Trade Secrets:** eFPGA RTL, precision CAD, and firmware binaries are kept strictly confidential.

---

### 10. Revision History

- **v2.2.1 (2026-09-17):**
  - **Added Modesty & Non-Exclusivity Notice (Chapter 0):** Invoked the intent of POLYLINK-HUD Section 0.9 to specify public prior art status and modesty notice.
  - **Generalized Technical Drafting Support & Legal Subject (Chapters 6, 8, 9):** Removed specific AI corporate names, applied v3.6 Appendix C standard wording, and reaffirmed the legal attribution of Sole Invention (deundeuni).
  - **Refined Target Design Benchmarks Tone (Chapters 4-1, 4-6):** Clarified quantitative specs as target design benchmarks and refined directional expressions (aims for).
- **v2.2 Final (2026-08-27):** Finalized 4-tier survival architecture (L0~L3) and L2 FSM specification; applied sub-classifications (Enterprise/Daily/Personal).
- **v2.0 (2026-08-25):** Declared defensive free publication of prior art; finalized the lowercase hyphenated name `soma-moa`.
- **v1.0 / v0.1 (2026-08-24):** Initial governance architecture planning for SOMA and OSRP.

---
origin: by deundeuni (soma-moa) - factory sample work & construction worker background  
domain: somamoa.ai.kr / Somamoa.ai.kr | repo: github.com/soma-moa  
Zenodo DOI: 10.5281/zenodo.22373538 / 22373722 / 22373704 / 22373189 / 22373686 / 22374987 (Registered / Active)  
prior art: 2026-08-25 | v2.2.1 Revision: 2026-09-17 | License: CC BY 4.0 & DPL
