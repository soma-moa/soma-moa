
soma-moa : Design Philosophy & Prior Art Declaration
> Original Design: deundeuni (soma-moa) | Repository: [github.com/soma-moa](https://github.com/soma-moa)
> Initial Record Date: 2026-08-24 | Prior Art Declaration Date: 2026-08-25 | v2.2.10 Revision (Safety Science Genealogy Expansion & Consistency Patch): 2026-09-21
> Technical Protocol Identifier: soma-moa | License: CC BY 4.0 and DPL (Defensive Publication License)
> Naming Definition: The term soma-moa (lowercase with hyphen) in this document is used as an open-source technical protocol identifier for public prior art declaration and codebase categorization, not as a commercial trademark.
> Originality Provision: The Korean original text (PHILOSOPHY.ko.md) serves as the primary benchmark source, and any translated versions are for reference only.
> 
This document is a record of why soma-moa was designed the way it is.
It is a record of the process, not just the result; of the thought trajectory, not merely the specifications.
0. A Design Rooted in the Native Language
soma-moa is not a technology that was conceived in English and translated into Korean.
It originated from hands-on knowledge accumulated while working in factories handling various machinery, performing sample operations, and working as a construction laborer on job sites. With the recent advent of AI, it started from the thought, "Could this also be developed into documentation?"
It is a protocol conceived deeply in Korean and proven through globally standardized code.
Therefore, moa is not an alias, but its true name.
While the English words gather and collect translate to "모은다" (gather), the emotional nuance of "embracing and gathering fragmented error logs and distributed terminals into one place" is exclusively conveyed in the Korean word moa.
This is the core identity and starting point of the design of soma-moa.
 * Modesty & Non-Exclusivity Notice:
   Although this protocol was conceived from the sole designer's daily life, site experiences, and reasoning, the possibility that similar technical concepts or ideas were independently researched by other investigators is not excluded. This document is publicly disclosed free of charge to prevent exclusive monopolization by any specific entity and to serve as public prior art that anyone can freely reference and build upon.
 * Barnacle Archetype Notice:
   It is explicitly stated that the barnacle biomimetic structure repeatedly appearing across this ecosystem (connector interfaces, ground structures, marine buoys, etc.) is not a simple stylistic preference, but was adopted and referenced as the initial biological archetype for the core governance philosophy of soma-moa: "surviving together by interlocking in layers and supporting the base, rather than enduring extreme environments as isolated individuals."
1. v0.1 OSRP - The Days of Bare Skeleton
Project Name: OSRP (Open Symbiotic Routine Protocol)
Initially, only the basic skeleton was established.
 * Zero-Trust Security: Connection is allowed exclusively via authorized networks, with sensor data directed straight to the internal network.
 * 3-Stage Escalation: WebRTC video call -> Telemetry logs -> Direct human technician dispatch.
 * Ultimate Human Control: Automated unilateral decisions by robots are constrained, ensuring the human right of intervention.
The word 'Routine' was discarded because it appeared as a simple scheduler and lacked intuitiveness as an engineering acronym.
2. v1.0 SOMA - Taking on a Body & Axiom 0
Project Name: SOMA (Symbiotic Operations & Machine Architecture)
The system matured into governance required for virtual AI to embody physical form (Greek Soma in reality).
 * Architectural Structure: Separated as an upper-tier governance layer responsible for safety and control, regardless of the hardware chassis (wheeled, quadrupedal, humanoid).
 * Enactment of Charter 0 (Axiom 0):
   "Robots/AI are subordinate (Sub), system governance is main (Main), but even that governance is merely auxiliary (Auxiliary) to primary human operations."
 * Horizontal Multi-System Principle:
   In horizontal relationships among multi-systems, all subsystems—including machinery, robots, and power systems—are defined as equal horizontal auxiliary means to support human productive activities within the system, rather than maintaining vertical dominance.
 * Instance of Inter-Entity Task Handover:
   When physical or computational limits occur among multi-robot or distributed terminal entities (e.g., between Robot A and Robot B) regarding battery level, distance, or compute capacity, the act of handing over task authority is performed not for autonomous negotiation based on individual machine interests, but for the "uninterrupted completion of human-directed productive activities." Each subsystem operates as an equal auxiliary entity mutually compensating for physical and computational weaknesses, aligning with the isomorphic co-survival governance logic based on L1/L2 specifications to secure overall system survival.
3. v1.5 Naming Search - Criteria After 20 Names
In addition to the English name SOMA, more than 20 candidate names were evaluated to find an easily pronounceable and intuitive name.
 * Bodeum, Gyeol, Irum — Pronunciation is somewhat heavy.
 * Nuri, Miso, Uri — Technical identity is not clearly communicated.
 * Gori, Dari, Sai — Scope is too narrow to encapsulate an entire N:1 gathering platform.
3 Established Criteria:
 * Must be pronounceable within 0.1 seconds.
 * Operational structure should be visualized upon hearing it.
 * Must contain scalability to gather distributed terminals as one.
4. v2.0 soma-moa - Systematization of Naming and Notation
Official Name: soma-moa by deundeuni
 * moa: The core essence of gathering scattered error logs and standards into one place.
 * Linguistic Symmetry: Visual and auditory rhythm alignment between S O M A (ㅗㅏ) and m o a (ㅗㅏ).
 * Lowercase Notation: Composed in lowercase hyphenated soma-moa for open-source protocol identity that developers can easily invoke in codebases.
4-1. v2.2 Reference Structure - 4-Tier Survival Architecture & L2 Finite State Machine (FSM) Specs
On top of the v2.0 name, the basic framework was systematized in v2.2.
 * L0 Physical Layer (Physical): CWP (Contactless Wireless Power transfer & differential deceleration docking) battery swapping + V-Home (V-groove Homing autonomous alignment module with ±5mm precision absorption) + 0.1ms hardware cutout emergency stop (targeting Motor EN PIN LOW control).
 * L1 Compute Layer (Compute): Chiplet-APU Many as One redundancy + CCS 70%/100ms Raft role rotation + Hard-shoulder 3-tier monitoring.
 * L2 Governance Layer (Governance): Physical separation of inference engine (Brain, probabilistic) vs. governance (Governance, deterministic) + eFPGA 0.1ms physical circuit breaker + Finite State Machine (FSM).
 * L3 Social Layer (Social): Quiet Assist haptic vibration (1-burst / 2-burst) + Anonymized delta logging with 10-second PII auto-destruction.
Edge Validation Parameters (Target Design Benchmarks):
CBOR L0 24B / L1 32B (each restricted below 50B), SDK 35.2KB (below 42KB), RAM 3.2KB (below 10KB), L0 synchronous 0.1ms HMAC hardware bypass / L1 asynchronous 2–5ms Ed25519.
Graduated Autonomy Principle:
Reflecting the practical limitation that humans cannot directly intervene in every anomalous situation, the L2 FSM adopts a ladder structure that delegates autonomy in stages. Following PRELOCK, the system first attempts horizontal cooperation among equal entities (HORIZONTAL_HANDOVER). If this fails to resolve anomalies in AI reasoning itself (Brain-Override) or physical hazards (E_STOP_LATCH), control is escalated to upper management and human intervention. This serves as a core design rationale to minimize human management fatigue (Quiet Assist philosophy in Chapter 4-2) while guaranteeing ultimate human authority (Charter 0).
L2 Finite State Machine (FSM) State Transition Conditions & Roles:
 * IDLE: Normal standby state.
 * MONITOR: Real-time monitoring of edge sensors and logs.
 * VALIDATE (<0.02ms): Deterministic safety rule verification via eFPGA.
 * PRELOCK (80%): Preemptive hardware lock preparation upon reaching an 80% risk probability threshold.
 * HORIZONTAL_HANDOVER: Preemptive handover of task authority to adjacent entities upon detecting limits in battery, distance, or compute performance (Human signature-free soft reset zone, aiming for uninterrupted human task continuity).
 * Brain-Override: Phase where L2 deterministic governance and human control physically override and invalidate abnormal control attempts by AI inference (Brain).
 * E_STOP_LATCH (<0.1ms): Latching motor power shutdown within 0.1ms.
 * RECOVERY: Maintains permanent latch state; recovery is prohibited without Ed25519 human signature approval.
4-2. v2.2 Expansion - From Daily Life to Job Sites
 * 3-Type AS Services: Remote/OTA (Over-The-Air updates), On-call dispatch, Resident (Hospitals, Factories, Department Stores, Logistics, Repair Centers, Food Courts).
 * Personalization: Medication/Todo/Health routines, Equipment repair history/warranties, Diet/Allergy tracking.
 * Expanded Search: Library librarian (Finding books via cover, mood, or synopsis) + Music search (Finding songs via humming, vibe, or lyrics).
4-3. v2.2 Sub-categorization - Moa into Enterprise / Daily / Personal
While moa gathers everything, execution must be segmented for lightweight operation. Thus, it is sub-categorized into three tiers:
 * Enterprise: Operational environments where continuous uptime is critical. Resident in factories, logistics, hospitals, and repair centers. Focuses on L0 0.1ms cutout control + L1 Many as One + L2 deterministic execution. Guarantees ultimate human decision-making.
 * Daily: Environments requiring exploration and support. Food courts, department store service centers, libraries, music. Focuses on Vibe Search + L3 escalation. Avoids definitive assumptions when confidence is below 90%, performing autonomous auxiliary inquiries instead.
 * Personal: Environments respecting individual privacy. Medication/Todo/Health, Diet/Allergies, Repair history. PII destroyed within 10s + 1-burst/2-burst haptics + minimizes indiscriminate logging.
Connecting everything while distributing the burden is the principle of Auxiliary.
4-4. Succession of Safety Philosophy - Safety Science Lineage & Hardware Implementation of soma-moa
soma-moa does not present an isolated, mutant theory; it inherits the legitimate 100-year lineage of Safety Science and aims to implement (embed) it at the hardware and embedded governance levels.
 * Heinrich (1931) Numerical Motivation: The 300:29:1 ratio serves as a historical cornerstone for safety frameworks. Rather than restricting the ratio to absolute numbers, it is cited as the primary motivation for gathering numerous near-misses and signals before a major disaster occurs.
 * Bird (1969) Structural Reinterpretation & Prevention of Concealment: Frank Bird recalculated the ratio to 1:10:30:600, shifting the cause of disasters from individual mistakes to defects in management systems and organizational structures. He proved that structural environments forcing workers to hide near-misses to avoid punishment or surveillance are the true root causes of major disasters.
 * Reason (1990) Active Interlocking of the Swiss Cheese Model: James Reason's Swiss Cheese Model explains that accidents occur when holes in multiple defensive layers (Latent Failures) align simultaneously. soma-moa does not leave latent failure risks unaddressed; instead, it uses L1 leukocyte fabric isolation scans, T-Reg 15% self-healing constraints, and L2 eFPGA Tri-State 3-phase isolation controls as an active hardware pipeline to seal cheese holes in real time.
 * Hollnagel (Safety-II) Resilience: Rather than focusing solely on accident prevention (Safety-I, minimizing failures), it focuses on Resilience—stabilizing and maintaining the 9,999 successful operational states. soma-moa implements this on hardware via L1 Many as One multi-unification and Raft consensus architecture.
 * Dekker (Just Culture) Hardware Internalization: Sidney Dekker's Just Culture warns that punitive surveillance systems ("Blame Culture") force workers to conceal accident data, jeopardizing the entire system. soma-moa embeds this culture of voluntary reporting and trust not as software policies, but as a deterministic hardware pipeline featuring L3 CBOR anonymized logging, 10-second PII auto-destruction, and minimal logging of minor errors.
 * Lineage Positioning of soma-moa: This protocol does not add a new safety theory. Instead, it dismantles the "surveillance systems that induce concealment" pointed out by Bird and Dekker, and embodies the mitigation of multiple defense layer defects and the Just Culture demanded by Reason, Hollnagel, and Dekker into field-embedded governance (Reason-based L1 leukocyte isolation, 10-second PII destruction, quiet haptic alerts, T-Reg 15% self-healing).
 * Harmony Between Field Work Values and Technology: Unilateral surveillance, loud alarm tones, and indiscriminate logging on job sites provoke worker bypass tactics and concealment rather than enhancing safety. Approaching governance as an "Auxiliary" support that respects worker dignity allows true symbiosis between humans and machines.
 * Quantitative Standards Adoption: Instead of relying on historical Heinrich/Bird ratios, formal industrial safety standards such as ISO 13849-1 Cat 4 PL e / IEC 61508 SIL3 / GDPR 5(1)(e) are cited as operational benchmarks.
> [S-01] Heinrich 1931 provides numerical motivation, and Bird 1969 offers structural reinterpretation; practical implementation relies on Reason's active Swiss Cheese containment, Safety-II, Just Culture, deterministic control, and anonymized near-miss hardware logging.
> 
4-5. Organic Interlocking & Preemptive Action Philosophy
Aims to complete preemptive measures within the field through organic interlocking.
 * L0 V-Home absorbs ±5mm physical alignment errors with precision.
 * L1 resolves anomalies within the fabric via 70% Raft re-election, 85% backpressure throttling, and leukocyte isolation.
 * L2 eFPGA executes deterministic lock control via 0.02ms VALIDATE and logs internal events.
Only in situations where internal resolution is impossible, L3 issues 1-burst/2-burst haptic notifications followed by WebRTC link to human managers, preserving technician dignity through ultimate human deference.
4-6. System Specification Summary
Major quantitative parameters per layer for prior art comparison and examination consistency (Target Design Benchmarks) are summarized as follows:
 * L0 Physical Latency — 0.1ms hardware emergency stop cutout control (Motor EN PIN LOW).
 * L0 Physical Error Absorption — V-Home Self-Align ±5mm precision absorption.
 * L0/L1 Verification Latency — L0 synchronous 0.1ms HMAC hardware bypass / L1 asynchronous 2–5ms Ed25519.
 * L1 Consensus Threshold — CCS Raft 70% agreement / 100ms role rotation.
 * L1 Backpressure Throttling — Automatic throttling upon detecting 85% fabric backpressure.
 * L1 Data Payload — CBOR packets L0 24B / L1 32B (each capped below 50B).
 * L2 Governance Verification Latency — eFPGA deterministic VALIDATE <0.02ms.
 * L2 Governance Lock Latch — E_STOP_LATCH <0.1ms physical power shutdown.
 * L2 Governance Predictive Threshold — PRELOCK preemptive shutdown prep upon reaching 80% risk probability.
 * L2 Governance Horizontal Handover — HORIZONTAL_HANDOVER resource and task transfer upon detecting limits.
 * L2 Governance Self-Healing Limit — T-Reg 15% limit and permanent isolation after 3 consecutive failures.
 * L3 Social Trust Threshold — Prohibition of definitive assumptions when Daily Vibe Search confidence is below 90%.
 * L3 Social PII Destruction Period — Anonymized delta logging destroyed within 10 seconds.
 * Edge Embedded Resource Constraints — SDK size 35.2KB (≤42KB), RAM 3.2KB (≤10KB).
5. Auxiliary Governance & Prior Art Declaration
Purpose of Disclosure (2026-08-25): This document publicly discloses minimum safety governance standards as prior art to mitigate the risk of exclusive patent monopolization by specific entities, establishing it as a public technology available to all.
 * Premise of Coexistence: "Arrive with a smile, leave with a smile."
 * Principle of Auxiliary Support: Governance performs a lightweight auxiliary role without disrupting primary tasks.
 * Deterministic Control: Even during abnormal AI behaviors, power bus cutoff is executed via L0 breakers.
5-1. Technician Dignity & Quiet Assist Protocol
 * Quiet Assist: Utilizes haptic 1-burst/2-burst alerts perceptible only to the worker instead of loud alarms.
 * Consideration Without Record: Minor simple errors are automatically deleted after 10 seconds to alleviate psychological burden, while physical hazard logs are retained.
 * Technician Respect Principle: Establishes technology value as an Auxiliary helper, not a surveillance tool.
Summary: Physical safety is decisively secured via L0 cutout control, while social safety is implemented through subtle haptic alerts and autonomous deletion rules.
5-2. Self-Healing Reset Philosophy - Soft Reset vs Hard Reset
 * Soft Reset (Autonomous Control, No Human Signature Required): L0/L1 self-healing — chiplet reboot, Raft re-election, token bucket reset, V-Home redocking, HORIZONTAL_HANDOVER entity transfer. Executed autonomously under T-Reg 15% limits and max 3-consecutive-failure isolation rules.
 * Hard Reset (Human Verification Mandatory): L2 E_STOP_LATCH release. Motor EN LOW latch release followed by the RECOVERY stage strictly requires Ed25519-based human cryptographic signature. Automated reboots are prohibited, complying with ISO 13849-1 / IEC 61508.
6. Technical Drafting Support & Legal Doctrine
 * Technical Drafting Support & Structuring: Generic Generative AI Text Refinement & Structuring Tools.
 * Role & Intellectual Property (IP) Attribution Notice: This document utilized generic generative AI text refinement and structuring tools for technical context structuring, proofreading, and expression smoothing. This notice is provided for role transparency; internal AI prompts and inference processes are not disclosed. All core technical conceptions, independent system architecture designs, final decisions, and IP ownership belong entirely to the original author (deundeuni / soma-moa).
 * Legal Doctrines Cited (USPTO / EPO / Case Law): Cites U.S. Supreme Court/CAFC precedent (Thaler v. Vidal), USPTO AI Inventorship Guidance (2024.02), and EPO Examination Guidelines (G-II 3.3.1) rejecting AI inventorship. Generic AI tools serve merely as technical drafting aids; the sole legal and technical conceiver of this invention is established as the human designer (deundeuni).
 * Standard Compliance: Aims for compliance with ISO 13849-1 Cat 4 / PL e, IEC 61508 SIL3, and GDPR 5(1)(e).
7. Defensive Rights & Technical Protocol Identifier Notice
 * Technical Protocol Identifier: soma-moa (lowercase with hyphen).
 * Technical Identifier Notice: The term soma-moa in this document is used as an open-source Technical Protocol Identifier for public prior art declaration and codebase distinction, not as a commercial trademark.
 * DPL Defensive Publication License Declaration: Disclosed under CC BY 4.0 and DPL (Defensive Publication License v1.0). Under DPL provisions, any entity referencing or citing this technical architecture cannot assert exclusive patent rights against it, mitigating patent trolling risks and securing the public domain defensively.
 * DPL Conditional Termination Clause: Includes a conditional retroactive termination clause stating that if an entity practicing this technology files a patent infringement lawsuit against the original author or ecosystem participants, license rights are deemed retroactively void.
8. Open Foundation Models, Sole Conception, and Attribution
This protocol originated from the reasoning of a sole designer (deundeuni). It began from real-world daily knowledge accumulated while operating machinery in factories, executing sample work, and participating in construction sites as a laborer.
soma-moa is a prior art record that systematized this field experience into globally standardized code.
General AI context refinement tools were reviewed as auxiliary drafting aids during this systematization process alongside Transformer architectures and open technical foundations. The legal and technical conceiver of all core concepts and architectural designs is deundeuni.
9. Sources & AS-IS Disclaimer
 * Safety Theories: Heinrich (1931) 300/29/1 — Numerical motivation; Bird (1969) 1:10:30:600 — Structural reinterpretation & management defects; Reason (1990) Swiss Cheese — Active containment of multiple defense layers; Hollnagel Safety-II/Resilience; Dekker (2012) Just Culture; Defense in Depth; Fail-Safe; ALARP.
 * Functional Safety: ISO 13849-1:2023 PL e, IEC 61508 SIL3, GDPR Article 5(1)(e).
 * Communication / Consensus: RFC 8949 CBOR, Ongaro 2014 Raft, HMAC-SHA256, Ed25519 RFC8032.
 * Legal: USPTO AI Inventorship Guidance 2024.02, Thaler v. Vidal 2022, EPO G-II 3.3.1.
 * License: CC BY 4.0 & DPL (Defensive Publication License v1.0).
 * Prior Art Verification Date & Zenodo DOIs: Prior art declaration: 2026-08-25 / Zenodo DOI: 10.5281/zenodo.22373538 / 22373722 / 22373704 / 22373189 / 22373686 / 22374987 (Registered / Active).
 * Verification & Drafting Tools: Generic Generative AI Text Refinement & Structuring Tools (Conception by deundeuni).
 * Target Figures & AS-IS Disclaimer: All quantitative figures (time, latency, thresholds) in this document serve as Target Design Benchmarks for maximum survivability; the 4-tier combination and governance philosophy constitute the core prior art. This document does not guarantee commercial operational completeness (Provided AS-IS). Practical industrial implementation requires professional engineer re-validation and field verification in accordance with relevant safety standards.
 * Trade Secrets: eFPGA RTL, precision CAD, and firmware binaries remain undisclosed.
10. Revision History
 * v2.2.10 Revision (2026-09-21):
   * Systematic Expansion of Safety Science Lineage & Positioning of soma-moa (Chapter 4-4): Systematized the safety science lineage: Heinrich (numerical motivation) → Bird (structural reinterpretation/prevention of concealment) → Reason (active Swiss Cheese containment) → Hollnagel (Safety-II success-oriented resilience) → Dekker (Just Culture). Clarified soma-moa as a field-embedded governance implementing these requirements via hardware pipelines (Reason-based L1 leukocyte isolation, 10s PII destruction, quiet haptics, T-Reg 15%).
   * Internal Consistency Adjustments: Corrected Chapter 1 typo, explicit interlocking of Reason's Swiss Cheese model between Chapters 4-4 and 4-5, and updated Chapter 9 sources and Footnote [S-01].
 * v2.2.9 Revision (2026-09-19):
   * Graduated Autonomy Principle Specified (Chapter 4-1): Systematized autonomy ladder structure balancing human management fatigue (Quiet Assist) with ultimate human authority (Charter 0), supplementing deterministic FSM state transition rationale.
 * v2.2.8 Revision (2026-09-19):
   * Barnacle Archetype Notice Added (Chapter 0): Clarified that the recurring barnacle biomimetic structure is an intentional biological motif representing "co-survival" governance under extreme conditions, reinforcing philosophical consistency and prior art defense.
 * v2.2.7 Revision (2026-09-18):
   * Defensive Tone Alignment: Adjusted definitive terms ("completed", "finalized") across the document to flexible expressions ("aiming for", "systematized", "reflecting interlocking") for defensive posture and future module expansions.
 * v2.2.6 Revision (2026-09-18):
   * English Term Normalization: Standardized major subheadings, metadata, and technical terms (FSM, Resilience, Provided AS-IS) with bilingual alignment.
 * v2.2.5 Revision (2026-09-18):
   * Added L2 FSM HORIZONTAL_HANDOVER State (Chapters 4-1, 4-6, 5-2): Reflected isomorphic interlocking with Chapter 2 Horizontal Auxiliary Principle.
   * Explicit L0 Terms (Chapter 4-1): Expanded CWP and V-Home definitions.
   * DPL Conditional Termination Clause (Chapter 7): Clarified retroactive voiding upon patent litigation.
   * Daily Vibe Search Alignment (Chapter 4-3): Synced <90% confidence inquiry rule between main text and summary tables.
   * RAM Limit Tightening (Chapters 4-1, 4-6): Tightened memory bounds to RAM 3.2KB (<10KB).
   * Direct Zenodo DOI Placement (Chapter 9): Placed DOIs directly for patent examiner timestamp verification.
 * v2.2.4 Revision (2026-09-18):
   * Technical Protocol Identifier Notice (Metadata, Chapter 7): Preemptively blocked trademark disputes by defining soma-moa strictly as an open-source technical identifier.
   * Horizontal Auxiliary Principle Instance (Chapter 2): Explicitly specified inter-robot resource/task handover as an instance of uninterrupted human productivity.
 * v2.2.3 Revision (2026-09-18):
   * Target Figures & AS-IS Disclaimer (Chapter 9): Defined Target Design Benchmarks and mandatory professional engineer re-validation rules.
 * v2.2.2 Revision (2026-09-18):
   * DPL Legal Definition (Chapters 7, 9): Defined Defensive Publication License mechanics preventing unauthorized patenting.
   * Domain Normalization (Metadata, Chapter 7): Standardized domain to lowercase somamoa.ai.kr.
   * L2 FSM Latch Figure (Chapter 4-6): Added E_STOP_LATCH <0.1ms power shutdown figure to summary table.
 * v2.2.1 Revision (2026-09-17):
   * Enacted Horizontal Multi-System Principle (Chapter 2): Defined human productivity assistance as the supreme constitutional rule over vertical machine hierarchies.
   * Modesty & Non-Exclusivity Notice (Chapter 0): Added public prior art declaration based on POLYLINK-HUD 0.9.
   * General Drafting Support Terms (Chapters 6, 8, 9): Standardized AI drafting tool disclosures and re-confirmed Sole Invention (deundeuni).
   * FSM Term & CBOR Payload Alignment (Chapters 4-1, 4-6): Unified Brain-Override and re-verified CBOR L0 24B / L1 32B (RAM 3.2KB) limits.
 * v2.2 Final (2026-08-27): Systematized 4-tier survival architecture (L0–L3) and L2 FSM specs; applied Enterprise/Daily/Personal sub-categorization.
 * v2.0 (2026-08-25): Public prior art declaration; established lowercase hyphenated soma-moa naming.
 * v1.0 / v0.1 (2026-08-24): Initial governance architecture design for SOMA and OSRP.
