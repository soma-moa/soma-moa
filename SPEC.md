# soma-moa : Spec v2.2 Final
> **domain:** `somamoa.ai.kr` | **repo:** `github.com/soma-moa`  
> **Initial Record Date:** 2026-08-27 | **Last Revised:** 2026-09-17 | **v2.2 Final (v2.2.1 Patch)**  
> **Status:** English Technical Standard | **Authoritative:** `PHILOSOPHY.ko.md` & `SPEC.ko.md`  
> **License:** CC BY 4.0 & DPL | **Origin:** by deundeuni (soma-moa)  
> **Authoritative Clause:** The Korean originals (`PHILOSOPHY.ko.md` / `SPEC.ko.md`) are authoritative; translations are for reference only.

---

### 1. Core Architecture

$$\text{[Brain: LLM/VLM Probabilistic]} \longrightarrow \text{[Governance: soma-moa Deterministic eFPGA]} \longrightarrow \text{[Actuator/APK]}$$

- **L0 Physical —** CWP Battery-Swap (60T/61T Diff) + V-Home Self-Align $\pm 5\text{mm}$ + $0.1\text{ms}$ HW Intercept E-Stop (Motor EN PIN LOW cutoff control)
- **L1 Compute —** Chiplet-APU Many as One Dual-Redundant + CCS $70\% / 100\text{ms}$ Raft Role-Swapping + Triple-Redundant Shoulder Control (Token Bucket + T-Reg $15\%$ + Tri-State)
- **L2 Governance —** Physical isolation of Brain vs Governance + eFPGA $0.1\text{ms}$ Blocker + FSM
  $$\text{IDLE} \longrightarrow \text{MONITOR} \longrightarrow \text{VALIDATE (<0.02ms)} \longrightarrow \text{PRELOCK (80\%)} \longrightarrow \text{Brain-Override} \longrightarrow \text{E\_STOP\_LATCH (<0.1ms)} \longrightarrow \text{RECOVERY}$$
- **L3 Social —** Quiet Assist 1x/2x Haptic + Anonymized Delta Logging PII $10\text{s}$ automatic deletion orientation + Just Culture

#### 1.1 Edge Quantitative Parameters & Constraints
- **CBOR Data Payload —** L0 24B (PII removed) / L1 32B (including 8B token), each $< 50\text{B}$ Array Encoding ($0.01\text{mm}$ quantization)
- **SDK Constraint —** $35.2\text{KB} < 42\text{KB}$ Zero-Dep C/Rust
- **RAM Memory —** $3.2\text{KB}$ ($100 \times 32\text{B}$, $10\text{s}$ volatile buffer)
- **Verification Latency —** L0 Sync $0.1\text{ms}$ HMAC HW Bypass / L1 Async $2\sim5\text{ms}$ Ed25519

---

### 1.2 Location Mapping - Enterprise/Daily/Personal Classifications

- **[A] Enterprise — High-Continuity Operational Environments (L0/L1/L2 Focused)**
  - Logistics Center — Vehicle numbers/dock assignments/safety training onboarding, L0 collision $0.1\text{ms}$ cutoff control, L1 inventory query integration.
  - Factory/Cloud Farm — Chiplet-APU Many as One + CCS Raft + $85\%$ backpressure throttling + leukocyte scan isolation.
  - Device Service Center (Laptops/Smartphones/Cameras) — Model name/serial/symptoms/warranty/repair history/engineer assignment integration. Resident terminals perform daily checks, L1 diagnostics, and L3 mediation without restart permissions.
  - Department Store/Hospital Resident — Returns/lost and found/VIP/missing child protection/multilingual response, L1 inventory query, and L3 escalation integration.

- **[B] Daily — Navigation & Convenience Support Environments (L3 + Vibe Search Focused)**
  - Food Court/Restaurant — Menu/allergens/queue numbers/seating/pickup calls and health routine integration. In case of allergen uncertainty, avoids guessing and executes L3 escalation.
  - Department Store Service Center Visitors — Lost and found/missing child protection/multilingual guidance support.
  - Library Librarian Vibe Search — Cover/feeling/synopsis-based book search when title is unknown.
  - Music Search — Humming/melody/feeling/lyrics context search. Connects to L3 when confidence is under $90\%$ rather than making assertive guesses.

- **[C] Personal — Privacy-Respecting & Low-Noise Environments (L3 Focused)**
  - Personal Custom — Medication/tasks/health routines, device repair history/warranty, diet/allergy management.
  - Quiet Assist — Utilizes haptic 1x (warning) / 2x (stop) notifications perceptible only to the operator instead of public alarms.
  - Recordless Care — Minor mistakes are automatically deleted after $10\text{s}$ to ease user burden, retaining logs only for physical safety hazards (GDPR 5(1)(e)).

---

### 1.3 Organic Self-Resolution Principle

Aims for an architecture where internal on-site cross-interlocking completes self-resolution prior to human intervention.

$$\text{Self-Resolvable Faults (Misalignment, Overload, Packet Bursts)} \longrightarrow \text{L0/L1/L2 Internal Resolution (Token Bucket, Raft, Tri-State, T-Reg)}$$
$$\text{Human Escalation (L3)} \longrightarrow \text{Reserved as a Last Resort to Minimize Fatigue}$$

- **L0 Self-Resolution —** Precision absorption and retry for V-Home $\pm 5\text{mm}$ physical errors, low-impact redocking via CWP differential (60T/61T Diff), self-reapplication attempt after $0.1\text{ms}$ E-Stop.
- **L1 Self-Resolution —** Throttling upon queue $85\%$ backpressure detection, CCS $70\%$ Raft $100\text{ms}$ re-election, leukocyte isolation buffer, T-Reg $15\%$ resource suppression, Tri-State permanent isolation.
- **L2 Self-Resolution —** eFPGA $0.02\text{ms}$ VALIDATE $\rightarrow$ $80\%$ PRELOCK $\rightarrow$ Brain-Override $\rightarrow$ E_STOP_LATCH internal latch control. Retains internal CBOR data without cloud logging.

---

### 2. Axiom 0

*"Robots and AI are auxiliary (Sub) while system governance is primary (Main); yet even governance itself is auxiliary (Auxiliary) to human primary operations."*  
Guarantees human final decision-making authority to cultivate a safe coexistence environment aimed at "smiling at arrival, smiling at departure."

---

### 3. Security & Self-Healing

Proof-of-Clearance (Ed25519), Cloud-Sign / Edge-Verify, CBOR L0 24B / L1 32B (each $< 50\text{B}$) Array Encoding ($0.01\text{mm}$ quantization), SDK $35.2\text{KB} < 42\text{KB}$ Zero-Dep C/Rust, RAM $3.2\text{KB}$ ($100 \times 32\text{B}$, $10\text{s}$ volatile buffer), L0 Sync $0.1\text{ms}$ HMAC HW Bypass / L1 Async $2\sim5\text{ms}$ Ed25519.

#### 3.1 APK Security & Integrity
- **Signature Verification & Integrity Control —** Blocks application execution upon integrity verification failure if a digital signature is missing.
- **Rooting & Jailbreak Countermeasures —** Preserves L2 Lock and Telemetry records upon detecting terminal rooting or jailbreaking to secure hardware safety.
- **Minimizing External Logging —** Avoids unauthorized cloud log collection and maintains a local safety preservation framework centered on internal CBOR-encoded data.

#### 3.2 Self-Healing Reset Classification (Soft Reset vs Hard Reset)
- **Soft Reset (Autonomous Control) —** Target: Chiplet reboot, Raft re-election, Token Bucket reset, V-Home redocking, leukocyte isolation release / Human Signature: Not required / Condition: T-Reg $15\%$ limit applied; permanent Tri-State isolation upon 3 consecutive chiplet failures / Basis: Safety-II Resilience, Graceful Degradation.
- **Hard Reset (Human Confirmation Mandatory) —** Target: Motor EN LOW E_STOP_LATCH release $\rightarrow$ RECOVERY / Human Signature: Ed25519 Human Sign-off mandatory (maintains permanent latch if unsigned) / Condition: Restricts auto-restart and aims for manual approval recovery / Basis: ISO 13849-1 Cat 4 PL e, IEC 61508 SIL3 Fail-Safe.

---

### 4. Escalation & Operations Framework

$$\text{L1 (BLE/MQTT-SN Haptic 1x/2x)} \longrightarrow \text{L2 (Lock \& Telemetry Risk Logging)} \longrightarrow \text{L3 (WebRTC Sign-off Human Approval)}$$

- **4.1 3-Tier After-Sales Service Framework —** Remote/OTA support, dispatch service, resident service (hospitals/factories/department stores/logistics/service centers/food courts). Resident staff lack restart authority and execute specification compliance rather than discretionary judgment.
- **4.2 Relationship Between Self-Resolution and Escalation —** Triggers L3 escalation only when self-resolution failure counter reaches 3 or T-Reg/Tri-State thresholds are exceeded, prioritizing the reduction of human management fatigue (Quiet Assist).

---

### 5. Safety Framework & Quantitative Standards

- **[S-01] Heinrich 1931 (300:29:1) —** Cited as historical and philosophical motivation; practical implementation rests on Safety-II, Just Culture, and anonymous near-miss reporting frameworks.
- **[S-02] Swiss Cheese (Reason 1990) —** Proactively blocks and mitigates defense line flaws.
- **[S-03] Defense in Depth —** Multi-layered defense system across all tiers.
- **[S-04] Fail-Safe —** Motor EN PIN LOW physical signal cutoff control.
- **[S-05] ALARP Expansion & Standard Compliance —** ISO 13849-1 Cat 4 PL e, IEC 61508 SIL3, GDPR Article 5(1)(e) PII $10\text{s}$ automatic deletion orientation.

#### 5.1 Application of Contemporary Safety Principles
- **Safety-II (Hollnagel) —** Focuses on stably maintaining the continuity of $9,999$ successful operational instances rather than solely preventing 1 accident (implemented via Many as One + Raft).
- **Just Culture —** Deletes minor mistakes after $10\text{s}$ and autonomous accident precursor reporting via anonymous CBOR logging.
- **Active Swiss Cheese Alignment —** Preemptively mitigates defense line hole formation through leukocyte scanning, T-Reg $15\%$, and Tri-State cutoff.

---

### 6. Article X & Extended Interfaces

- **Article X —** Governed via dual I/O requirements regardless of hardware chassis type (wheeled/quadrupedal/humanoid). Brain (AI) acts in a proposal-only capacity, while Governance executes deterministic final enforcement.
- **6.1 Vibe Search —** Library book search (cover/feeling/synopsis) and music humming search (melody/feeling/lyrics) integration. Executes L3 escalation when confidence is below $90\%$ rather than making assertive guesses.

---

### 7. Specification Verification & Standards

- **Communication & Consensus Standards —** CBOR RFC 8949, Raft Ongaro 2014, HMAC-SHA256, Ed25519 RFC 8032.
- **Functional Safety & Legal Compliance —** ISO 13849-1:2023 PL e, IEC 61508 SIL3, GDPR 5(1)(e), USPTO AI Inventorship Guidance (2024.02), Thaler v. Vidal (2022), EPO G-II 3.3.1.

---

### 8. Open Foundational Models & Attribution

This protocol originated from everyday reflection derived from the single system architect's (`deundeuni`) hands-on experience with sheet metal machinery and daily labor at semiconductor construction sites.

During the systematization process, open-source AI models (large language models, etc.) were utilized as auxiliary drafting and verification tools (for cross-checking technical context, verifying quantitative figures, and structuring standardized markdown formats). Open-source AI models served as auxiliary documentation tools, while primary technical conception and independent architectural design authority reside exclusively with `deundeuni` (in compliance with USPTO 2024 AI Inventorship Guidance).

Trade secrets including eFPGA RTL source code, precision CAD drawings, and firmware binary sources remain strictly confidential.

---

### 9. Prior Art Registration & Target Figures Disclaimer

- **Prior Art Global Registry Filings (Zenodo DOIs / GitHub Repositories) —**
  - `deundeuni/CWP-Battery-Swap` (DOI: `10.5281/zenodo.22373538`)
  - `deundeuni/CWP-Clamping-Battery-Swap-System` (DOI: `10.5281/zenodo.22373722`)
  - `deundeuni/CWP-Rolling-Self-Align-Battery-Swap-System` (DOI: `10.5281/zenodo.22373704`)
  - `deundeuni/LAST-LIGHT` (DOI: `10.5281/zenodo.22373189`)
  - `deundeuni/MAX-LIFE-ICE-BELT` (DOI: `10.5281/zenodo.22373686`)
  - `deundeuni/chiplet-apu-multi-system-survival-architecture` (DOI: `10.5281/zenodo.22374987`)
  *(Active listings on CERN Zenodo / DataCite global academic registry)*

- **Target Technical Figures & AS-IS Disclaimer —** All quantitative parameters (durations, response latencies, thresholds, capacity metrics) specified in this standard represent **Target Technical Figures & Guidelines** aimed at achieving optimal system survival and do not guarantee commercial operational completeness (Provided AS-IS). Practical industrial implementation mandates re-verification by professional engineers according to applicable safety standards and site-specific operating conditions.

- **Unintentional Omission & Non-Limiting Provision —** Cited standards and repository listings serve as illustrative examples and do not imply exhaustive limitation. Derived revisions or equivalent prior art omitted due to subjective human limitations are considered within the scope of defensive publication prior art.

---
origin: by deundeuni (soma-moa) | domain: somamoa.ai.kr / Somamoa.ai.kr | repo: github.com/soma-moa
Initial: 2026-08-27 | Revised: 2026-09-17 | v2.2 Final (v2.2.1 Patch) | PHILOSOPHY.ko.md & SPEC.ko.md are authoritative | License: CC BY 4.0 & DPL
