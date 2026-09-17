# soma-moa : Design Philosophy & Prior Art Declaration
> **original design:** `deundeuni (soma-moa)` | **repository:** `github.com/soma-moa`  
> **initial record date:** 2026-08-24 | **prior art declaration:** 2026-08-25 | **v2.2.7 Defensive Tone Revision:** 2026-09-18  
> **technical identifier:** `soma-moa` | **License:** CC BY 4.0 & DPL (Defensive Publication License)  
> **Naming Pre-definition:** The term `soma-moa` (lowercase hyphenated) in this document is used not as a commercial trademark, but as an open-source technical protocol identifier for prior art disclosure and codebase distinction.  
> **Master Original Clause:** The Korean original text (PHILOSOPHY.ko.md) serves as the primary master source, and translations (including PHILOSOPHY.md) are for reference purposes only.

This document is a record of why `soma-moa` was designed this way.  
It is a trace of process rather than result, of reasoning rather than specs.

---

### 0. Design Started in Native Language (모국어로 시작한 설계)

soma-moa was not built in English first and then translated into Korean.  
It began with knowledge accumulated in daily life—handling various machines for sample work in factories and working as a construction laborer. With recent encounters with AI, it started from the thought, "Could I make structured documentation out of this experience?"

It is a protocol conceived deeply in Korean and proven through globally compliant code.  
Therefore, `moa (모아)` is not a nickname, but its true name.

While the English words "gather" or "collect" are translated as "모은다", the warmth of "embracing and gathering fragmented error logs and distributed terminals into one place" is contained uniquely in the Korean word 'moa'.

This is the identity of soma-moa and the starting point of its design.

**Modesty & Non-Exclusivity Notice (독립적 선행 연구 및 무독점 고지):**  
Although this protocol was conceived from the individual designer's daily life, field experience, and reasoning, the possibility that similar technical ideas or concepts were independently researched earlier by other researchers is not excluded. This document is disclosed free of charge as public Prior Art to prevent exclusive monopolization by specific entities and to allow anyone to freely reference and develop it.

---

### 1. v0.1 OSRP - Days of Pure Skeleton

**Project Name: OSRP (Open Symbiotic Routine Protocol / 개방형 유기적 루틴 프로토콜)**

Initially, only the basic skeleton was established:
- **Zero Trust Security:** Only approved networks are allowed to connect, and sensor data is directed strictly to internal networks.
- **3-Stage Escalation:** WebRTC video call -> Telemetry log -> Direct human dispatch.
- **Human Final Control:** Restrict situations where robots make autonomous decisions and guarantee human intervention rights.

The word 'Routine' was discarded because it appeared like a simple scheduler, lacking intuitive engineering clarity.

---

### 2. v1.0 SOMA - Wearing the Physical Form & Axiom 0

**Project Name: SOMA (Symbiotic Operations & Machine Architecture / 공생적 운용 및 기계 아키텍처)**

The governance expanded in scale when virtual AI assumed a physical body (Greek *Soma*) in reality.

- **Architectural Structure:** Separated into an upper governance layer handling safety and control regardless of the hardware chassis form factor (wheeled, quadrupedal, humanoid).
- **Enactment of Axiom 0 (0번 헌장):**  
  *"Robots/AI are Sub, System Governance is Main, but even that Governance is Auxiliary to human primary work."*
- **Horizontal Multi-System Principle (수평적 다중 시스템 보조 원칙):**  
  In a multi-system horizontal relationship, machines, robots, power systems, and all subsystems are defined as means to assist human productive activities within the system, avoiding vertical hierarchical dominance. (In a multi-system horizontal relationship, machines, robots, power systems, and all subsystems are defined as means to assist human productive activities within the system.)
- **Instance of Inter-Entity Task Handover & Work Continuity (수평적 역할 이행 및 작업 연속성 실시예):**  
  When physical constraint situations occur among multi-robot or distributed terminal entities (e.g., Robot A and Robot B) regarding battery level, proximity distance, or compute performance, the act of transferring task initiative is performed for the purpose of **"uninterrupted completion of human-instructed productive activities"**, rather than autonomous negotiation based on individual machine interests. Each subsystem operates as an equal auxiliary subject mutually compensating for physical and computational weaknesses, aiming to connect to the implementation of an isomorphic together-survival governance logic based on L1/L2 whitepapers to secure overall system survival.

---

### 3. v1.5 Naming Exploration - Standards After 20 Names

In addition to the English name SOMA, over 20 names were reviewed to find an intuitive and easy-to-pronounce identifier.

- **Bodeum, Gyeol, Irum** — Pronunciation felt somewhat heavy.
- **Nuri, Miso, Uri** — Technical identity was not clearly communicated.
- **Gori, Dari, Sai** — Scope was too limited to encompass an N:1 collecting platform.

**3 Established Criteria:**
1. Must be pronounceable within 0.1 seconds
2. Operational structure must be visualized upon hearing it
3. Must contain scalability to gather distributed terminals into one

---

### 4. v2.0 soma-moa - Systematization of Name & Notation

**Official Name: soma-moa by deundeuni**

- **moa (모아):** The essence of gathering scattered error logs and standards into one place.
- **Linguistic Symmetry:** Visual and auditory rhythm alignment between S O M A (ㅗㅏ) - m o a (ㅗㅏ).
- **Lowercase Notation:** Formatted as lowercase hyphenated `soma-moa` to reflect its identity as an open-source protocol easily referenced by developers in codebases.

---

### 4-1. v2.2 Baseline Structure - 4-Tier Survival Architecture & L2 Finite State Machine (FSM) Specification

Building upon v2.0, the baseline system structure was systematized in v2.2.

- **L0 Physical Tier:** CWP (Contactless Wireless Power / 무선 전력 전송 및 차동 감속 도킹) Battery-Swap + V-Home (V-groove Homing / V-홈 자율정렬 모듈, ±5mm alignment) Self-Align + 0.1ms Hardware Intercept E-Stop (aiming for Motor EN PIN LOW cutoff control)
- **L1 Compute Tier:** Chiplet-APU Many as One Dual-Redundant + CCS 70%/100ms Raft Role-Swapping + Shoulder Lane (Auxiliary Path) 3-tier Control
- **L2 Governance Tier:** Brain (Probabilistic) vs Governance (Deterministic) physical separation + eFPGA 0.1ms Blocker + Finite State Machine (FSM)
- **L3 Social Tier:** Quiet Assist Haptic 1x/2x + Anonymized Delta Logging PII 10-second destruction

**Edge Design Benchmarks (Target Design Benchmarks):** CBOR L0 24B / L1 32B (each restricted within <50B limit), SDK 35.2KB (<42KB), RAM 3.2KB (<10KB), L0 Sync 0.1ms HMAC HW Bypass / L1 Async 2~5ms Ed25519

**L2 FSM State Transition Conditions & Role Definitions:**
- **IDLE (대기):** Normal standby state
- **MONITOR (감시):** Real-time monitoring of edge sensors and telemetry logs
- **VALIDATE (검증, <0.02ms):** eFPGA-based deterministic safety rule validation
- **PRELOCK (선제 잠금, 80%):** Preemptive hardware locking preparation upon reaching 80% hazard probability
- **HORIZONTAL_HANDOVER (수평 이양):** Preemptive task initiative transfer to adjacent entity upon detecting battery, distance, or compute limits (Soft Reset domain requiring no human signature, aiming for human task continuity)
- **Brain-Override (Brain 우위 무효화):** Stage where L2 deterministic governance and human control physically override and nullify anomalous AI inference (Brain) control attempts
- **E_STOP_LATCH (비상 정지 래치, <0.1ms):** Motor power cutoff latching within 0.1ms
- **RECOVERY (복구):** Permanent latch state maintained; recovery prohibited without Ed25519 human signature approval

---

### 4-2. v2.2 Expansion - From Everyday Life to On-Site

- **3 AS Services:** Remote/OTA, Dispatch, Resident (Hospital / Factory / Department Store / Logistics / Repair Center / Food Court)
- **Personal Customization:** Medication / Task / Health Routines, Device Repair History / Warranty, Diet / Allergies
- **Extended Search:** Library Librarian (searching books by cover / feel / summary) + Music Search (searching by humming / vibe / lyrics)

---

### 4-3. v2.2 Sub-classification - Enterprise / Daily / Personal

While `moa` gathers everything, application must be categorized to remain lightweight. Thus, it was divided into 3 sub-categories.

- **Enterprise (기업용):** Operating environments where operational continuity is critical. Factories, logistics, hospitals, AS centers. L0 0.1ms cutoff control aiming + L1 Many as One + L2 deterministic execution focus. Guarantees final human judgment.
- **Daily (일상용):** Environments requiring exploration and assistance. Food courts, department store service counters, libraries, music. Vibe Search + L3 escalation focus. Avoids definitive speculation when confidence is below 90% and performs autonomous auxiliary inquiry.
- **Personal (개인용):** Environments respecting personal privacy. Medication / task / health, diet / allergy, repair history. PII 10-second destruction + Haptic 1x/2x + aiming to minimize unnecessary logging.

Connecting all while distributing load is the core principle of `Auxiliary (보조)`.

---

### 4-4. Succession of Safety Philosophy - Heinrich as Motivation Only

Heinrich 300:29:1 is a philosophical foundation enacted in 1931. Rather than limiting the ratio to absolute numbers, it is cited as a motivation for why preventive measures must be gathered.

Actual implementation is expanded and applied based on modern safety frameworks:
- **Safety-II / Resilience (Hollnagel):** Focuses on maintaining 9,999 normal operating conditions safely rather than solely preventing accidents. Implemented via Many as One and Raft-based architecture.
- **Just Culture & Anonymous Reporting:** CBOR anonymous logging + PII 10-second destruction + minor item logging minimization applied to foster autonomous reporting culture.
- **Activating Swiss Cheese Model:** Actively detecting defense line leakage risks to achieve preemptive defect mitigation via Leukocyte Scan, T-Reg 15%, and Tri-State disconnects.
- **Establishing Quantitative Standards:** Citing formal standard parameters such as ISO 13849-1 Cat 4 PL e / IEC 61508 SIL3 / GDPR Article 5(1)(e) instead of Heinrich ratios.

> [S-01] Heinrich 1931 is cited as historical and philosophical motivation; actual implementation relies on Safety-II, Just Culture, deterministic control, and anonymous near-miss reporting systems.

---

### 4-5. Organic Interlock & Preemptive Action Philosophy

Aims to complete preemptive measures within the field through organic interlocking:

- At L0, V-Home precisely absorbs physical errors within ±5mm range
- At L1, aims for internal fabric resolution via 70% Raft re-election, 85% backpressure, and Leukocyte isolation
- At L2, eFPGA performs lock control within 0.02ms VALIDATE and logs internally

Only when self-resolution is unattainable does L3 issue Haptic 1x/2x notifications followed by WebRTC human manager interlock, preserving technician dignity through final reservation of human judgment.

---

### 4-6. System Specification Summary (정량 핵심 스펙 명세)

The overall quantitative parameter specifications (Target Design Benchmarks) for each tier, provided for prior art comparison and review alignment, are as follows:

- **L0 Physical Latency —** 0.1ms Hardware E-Stop cutoff control aiming (Motor EN PIN LOW)
- **L0 Physical Error Absorption —** V-Home Self-Align ±5mm precision absorption
- **L0/L1 Verification Latency —** L0 Sync 0.1ms HMAC HW Bypass / L1 Async 2~5ms Ed25519
- **L1 Compute Consensus Threshold —** CCS Raft 70% consensus / 100ms Role-Swapping
- **L1 Compute Backpressure —** Automatic throttling upon detecting 85% internal fabric backpressure
- **L1 Compute Data Payload —** CBOR packet L0 24B / L1 32B (each restricted within <50B limit)
- **L2 Governance Verification Latency —** eFPGA deterministic VALIDATE <0.02ms
- **L2 Governance Cutoff Latch —** E_STOP_LATCH <0.1ms physical power disconnect
- **L2 Governance Prediction Threshold —** PRELOCK 80% hazard probability preemptive cutoff prep
- **L2 Governance Horizontal Handover —** HORIZONTAL_HANDOVER entity resource and task handover upon detecting constraint limits
- **L2 Governance Self-Healing Constraint —** T-Reg 15% limit and permanent isolation after 3 failures
- **L3 Social Confidence Threshold —** Daily Vibe Search avoids definitive speculation under 90% confidence
- **L3 Social PII Destruction Period —** Anonymized Delta Logging destroyed within 10 seconds
- **Edge Embedded Resource Constraints —** SDK size 35.2KB (<42KB), RAM 3.2KB (<10KB)

---

### 5. Auxiliary Governance & Prior Art Declaration (보조 거버넌스 및 선행기술 공개)

**Disclosure Purpose (2026-08-25):** This document discloses the minimum safety auxiliary specifications as prior art for human-AI-robot coexistence to mitigate exclusive patent monopolization risks by specific entities and establish it as public technology accessible to all.

- **Premise of Coexistence:** "Smile on the way to work, smile on the way home"
- **Principle of Auxiliary:** Governance performs a lightweight auxiliary role without interfering with primary work
- **Deterministic Control:** Aiming for power bus cutoff control via L0 blocker even during anomalous AI behaviors

---

### 5-1. Technician Dignity & Quiet Assist Protocol (기술자 존엄 및 조용한 보조 프로토콜)

- **Quiet Assistance:** Utilizes haptic 1x/2x vibration notifications perceptible only to the worker instead of excessive alarm sounds
- **Consideration Without Logging:** Eases psychological burden by automatically deleting minor simple mistakes after 10 seconds while maintaining logs for physical hazard items
- **Technician Treatment Principle:** Establishes value as an auxiliary partner rather than a surveillance tool

**Summary:** Physical safety is explicitly secured via L0 cutoff control, while social safety is gently implemented through vibration alerts and autonomous deletion clauses.

---

### 5-2. Self-Healing Reset Philosophy - Soft vs Hard Reset (자가치유 리셋 철학)

- **Soft Reset (Autonomous control, no human signature required):** L0/L1 self-healing — Chiplet reboot, Raft re-election, Token Bucket reset, V-Home re-docking, HORIZONTAL_HANDOVER entity handover. Autonomous execution under T-Reg 15% limit and permanent isolation after 3 consecutive failures.
- **Hard Reset (Human confirmation mandatory):** L2 E_STOP_LATCH release. The RECOVERY stage following Motor EN LOW latch release strictly requires Ed25519-based human signature. Avoids automatic rebooting and complies with ISO 13849-1 / IEC 61508 standards.

---

### 6. Technical Drafting Support & Legal Doctrine (기술 작성 지원 및 법리적 주체 명시)

- **Technical Drafting & Structuring Support:** Generic Generative AI Text Refinement & Structuring Tools
- **Role & IP Attribution Notice:** This document utilized generic generative AI text refinement and structuring tools for structural formatting, verification support, and expression mitigation. This disclosure is for role transparency; AI prompts and internal reasoning processes are not disclosed. All core technical conception, independent system architecture design, final decisions, and intellectual property (IP) ownership belong entirely to the original author (deundeuni / soma-moa).
- **Legal Doctrines Cited (USPTO / EPO / Case Law):** Cites US Supreme Court/CAFC precedent (*Thaler v. Vidal*), USPTO AI Inventorship Guidance (2024.02), and EPO Examination Guidelines (G-II 3.3.1) denying AI inventorship. Generic AI tools serve merely as technical document refinement aids; the sole inventorship entity of this technical system is legally established as the human designer (deundeuni).
- **Standard Compliance:** Aiming for compliance with ISO 13849-1 Cat 4 / PL e, IEC 61508 SIL3, GDPR Article 5(1)(e).

---

### 7. Defensive Rights & Technical Protocol Identifier Notice (실리보호 및 기술 프로토콜 명칭 고지)

- **Technical Protocol Identifier:** `soma-moa` (lowercase hyphenated)
- **Technical Identifier Notice:** The term `soma-moa` in this document is used not as a commercial trademark, but as an **Open-Source Technical Protocol Identifier** for public prior art disclosure and codebase distinction.
- **DPL Defensive Publication License Declaration:** This protocol is released under CC BY 4.0 and DPL (Defensive Publication License v1.0). Under DPL terms, other entities referencing or citing this technical concept cannot claim exclusive patent rights over it, mitigating unauthorized patent private monopolization risks by third parties and defensively expanding the public technical domain.
- **DPL Conditional License Termination Clause:** This DPL includes a conditional retroactive termination clause stating that if any entity practicing this technology files a patent infringement lawsuit against the original author or ecosystem participants, the license intent toward said practicing entity shall be deemed retroactively non-existent.

---

### 8. Open Foundation Models & Sole Design Attribution (개방된 기반 모델과 1인 설계 및 출처)

This protocol originated from the thoughts of a single designer (deundeuni). It began from practical daily knowledge accumulated while handling factory machinery for sample work and participating as a construction laborer on job sites.

soma-moa is a prior art record that systemizes these field observations into globally compliant code.

In this systemization process, Transformer architectures and open technical foundations were reviewed alongside generic AI text refinement tools as auxiliary aids. The legal and technical entity of all core conceptions and independent architectural designs belongs to deundeuni.

---

### 9. Sources & Prior Art Evidence / AS-IS Disclaimer (출처 및 선행기술 근거)

- **Safety Theory:** Heinrich (1931) 300/29/1 — Philosophical motivation, Reason (1990) Swiss Cheese, Hollnagel Safety-II/Resilience, Defense in Depth, Fail-Safe, ALARP, Just Culture
- **Functional Safety:** ISO 13849-1:2023 PL e, IEC 61508 SIL3, GDPR Article 5(1)(e)
- **Communication/Consensus:** RFC 8949 CBOR, Ongaro 2014 Raft, HMAC-SHA256, Ed25519 RFC8032
- **Legal Precedents:** USPTO AI Inventorship Guidance 2024.02, Thaler v. Vidal 2022, EPO G-II 3.3.1
- **Licenses:** CC BY 4.0 & DPL (Defensive Publication License v1.0)
- **Prior Art Declaration Date & Registered DOIs:** prior art declaration: 2026-08-25 / Zenodo DOI: 10.5281/zenodo.22373538 / 22373722 / 22373704 / 22373189 / 22373686 / 22374987 (Active)
- **Verification & Documentation Tools:** Generic Generative AI Text Refinement & Structuring Tools (Conception by deundeuni)
- **Target Figures & AS-IS Disclaimer:** All quantitative figures (time, latency, thresholds, etc.) in this document represent Target Design Benchmarks for maximum survival capability, while the 4-Tier coupled structure and governance philosophy constitute the primary prior art. This document does not guarantee commercial operational completeness (Provided AS-IS); actual industrial implementation requires multi-stage field re-validation by professional engineers according to relevant safety standards.
- **Trade Secrets:** eFPGA RTL, precision CAD, and firmware binaries remain undisclosed.

---

### 10. Revision History & Alignment Patch Log (변경 이력 및 정합화 패치 기록)

- **v2.2.7 Revision (2026-09-18):**
  - **Defensive Tone Refinement & Shoulder Lane Terminology Patch:** Replaced over-assertive/definitive terms throughout the text with defensive phrasing. Refined L1 Shoulder path term to `Shoulder Lane (Auxiliary Path) 3-tier Control` in 1:1 alignment with Korean master text.
- **v2.2.6 Revision (2026-09-18):**
  - **English Text Normalization & Isomorphic Alignment:** Standardized all headings, metadata, and technical terms into 1:1 bilingual structure matching PHILOSOPHY.ko.md.
- **v2.2.5 Revision (2026-09-18):**
  - **Added L2 FSM `HORIZONTAL_HANDOVER` State (Sections 4-1, 4-6, 5-2):** Reflected code/state machine isomorphic interlock with Section 2 horizontal auxiliary principle.
  - **Explicit L0 Physical Acronym Definitions (Section 4-1):** Added full expansions for CWP (Contactless Wireless Power) and V-Home (V-groove Homing, ±5mm self-alignment).
  - **Explicit DPL Conditional Retroactive Termination Clause (Section 7):** Clarified clause regarding retroactive non-existence of license intent upon filing patent lawsuits.
  - **Normalized Daily Tier 90% Confidence Threshold (Section 4-3):** Aligned body text with Section 4-6 summary spec.
  - **Refined RAM Limit (Sections 4-1, 4-6):** Tightened defense range to `RAM 3.2KB (<10KB)`.
  - **Direct Placement of Zenodo DOIs in Section 9:** Placed timestamp verification DOIs directly in Section 9 for examiner access.
- **v2.2.4 Revision (2026-09-18):**
  - **Trademark Dispute Prevention & Technical Identifier Definition (Metadata, Section 7):** Established `soma-moa` strictly as an open-source Technical Protocol Identifier.
  - **Refined Horizontal Principle Instance (Section 2):** Explicitly detailed inter-entity task handover as an isomorphic together-survival instance for human task completion.
- **v2.2.3 Revision (2026-09-18):**
  - **Target Figures & AS-IS Disclaimer Enhancement (Section 9):** Designated benchmarks and added Provided AS-IS / mandatory engineer re-validation clauses.
- **v2.2.2 Revision (2026-09-18):**
  - **DPL Legal Definition Definition (Sections 7, 9):** Defined anti-patent-privatization defense scope.
  - **Domain Normalization (Metadata, Section 7):** Standardized domain to lowercase `somamoa.ai.kr`.
  - **L2 FSM Cutoff Latch Addition (Section 4-6):** Added `E_STOP_LATCH <0.1ms` parameter.
- **v2.2.1 Revision (2026-09-17):**
  - **Enacted Horizontal Multi-System Auxiliary Principle (Section 2):** Defined human productive assistance as supreme rule.
  - **Independent Prior Art & Non-Exclusivity Notice (Section 0):** Added modesty notice citing POLYLINK-HUD 0.9.
  - **Generalized Generative AI Drafting Support (Sections 6, 8, 9):** Applied standard AI tool documentation clauses and reaffirmed Sole Invention by deundeuni.
  - **FSM & CBOR Re-alignment (Sections 4-1, 4-6):** Unified `Brain-Override` state and verified CBOR L0 24B / L1 32B (RAM 3.2KB) parameters.
- **v2.2 Final (2026-08-27):** Systematized 4-Tier Survival Architecture (L0~L3) and L2 FSM spec, applied sub-categories.
- **v2.0 (2026-08-25):** Declared defensive publication prior art, established lowercase hyphenated `soma-moa`.
- **v1.0 / v0.1 (2026-08-24):** Initial SOMA and OSRP governance architecture planning.

---
origin: by deundeuni (soma-moa) - factory sample work & construction worker background  
repository: github.com/soma-moa  
Zenodo DOI: 10.5281/zenodo.22373538 / 22373722 / 22373704 / 22373189 / 22373686 / 22374987 (Active)  
prior art: 2026-08-25 | v2.2.7 Revision: 2026-09-18 | License: CC BY 4.0 & DPL
