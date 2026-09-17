# soma-moa : Human-Centered Physical AI & Spatial Governance Protocol
> **original design:** `deundeuni (soma-moa)` | **repository:** `github.com/soma-moa`  
> **domain:** `somamoa.ai.kr` | **v2.2.1 Revision:** 2026-09-17 | **License:** CC BY 4.0 & DPL  
> **Document Status:** The Korean text (README.ko.md / PHILOSOPHY.ko.md) is the authoritative original; translations are for reference only.

### 0. Definition
soma-moa is a protocol for visitor guidance and spatial assistant robots designed to start from everyday environments and gracefully expand into various operational fields—such as hospitals, factories, building lobbies, department store service centers, logistics centers, device repair centers (laptops/smartphones/cameras), and food court/restaurant unmanned assistants.

### 1. Axiom 0
"Robot/AI is Sub, system governance is Main, but even that governance is Auxiliary to the human's main task."

### 2. Core Architecture
$$\text{[Brain]} \longrightarrow \text{[Governance: soma-moa eFPGA]} \longrightarrow \text{[Actuator/APK]}$$
 * **Article X Specification** — Aims for uniform integrated control under top-level I/O dual requirements regardless of hardware chassis forms (wheels, quadrupeds, humanoids, kiosks, holograms, or snowballs).

### 3. 4-Layer Survival System
 * **L0 Physical** — CWP Battery-Swap + V-Home Self-Align $\pm 5\text{mm}$ + $0.1\text{ms}$ physical cutoff line E-Stop (aims for Motor EN PIN LOW cutoff control)
 * **L1 Compute** — Chiplet-APU Many as One Dual-Redundant + CCS $70\% / 100\text{ms}$ Raft non-stop role-swapping + triple-redundant shoulder control (Token Bucket + T-Reg $15\%$ + Tri-State)
 * **L2 Governance** — Brain (Probabilistic) vs Governance (Deterministic) physical separation + eFPGA $0.1\text{ms}$ Deterministic Blocker
 * **L3 Social** — Quiet Assist haptic 1x/2x + Anonymized Delta Logging (aims for PII $10\text{s}$ automatic deletion)

### 4. Edge Verification
 * **CBOR Payload Examples** — Serialization and memory padding included, each targeting $< 50\text{B}$ (L0 $\sim 24\text{B}$ PII removed, L1 $\sim 32\text{B}$ 8B token) ($0.01\text{mm}$ quantization)
 * **Embedded Constraints** — SDK size $35.2\text{KB} < 42\text{KB}$ Zero-Dep C/Rust, RAM $3.2\text{KB}$ (based on 32B $\times$ 100 Logs)
 * **Sync/Async Latency** — L0 Sync $0.1\text{ms}$ HMAC Hardware Bypass / L1 Async $2\sim5\text{ms}$ Ed25519

```rust
// Struct sizes are target example values including Rust compiler #[repr(C)] memory layout padding.
// L0 Critical Log Structure (~24 Bytes Target)
#[repr(C)]
pub struct L0CriticalLog {
    pub ts_offset: u32,    // 4B
    pub sev: u8,           // 1B
    // implicit padding: 1B (Alignment for i16)
    pub delta_q: [i16; 6], // 12B
    pub gov: bool,         // 1B
    // implicit padding: 1B (Alignment for u16)
    pub crc: u16,          // 2B
    // implicit padding: 2B (Struct alignment to 4-byte boundary)
} // Total memory layout: 24B

// L1 Warning Log Structure (~32 Bytes Target)
#[repr(C)]
pub struct L1WarningLog {
    pub ts_offset: u32,    // 4B
    pub sev: u8,           // 1B
    // implicit padding: 3B (Alignment for u64)
    pub op_token: u64,     // 8B
    pub delta_q: [i16; 6], // 12B
    pub gov: bool,         // 1B
    // implicit padding: 1B (Alignment for u16)
    pub crc: u16,          // 2B
} // Total memory layout: 32B
```

### 5. Location Mapping
 * **Enterprise** — Logistics centers, factories, AS centers, department store/hospital residency, etc., focusing on operational continuity environments (residency terminals not granted restart authority).[A]
 * **Daily** — Food courts, libraries, music search, etc., focusing on Vibe Search environments (avoids assertive guessing when confidence is below 90%).[B]
 * **Personal** — Medication/to-do/health/diet/repair history, etc., personalized environments (aims for PII $10\text{s}$ destruction + haptic 1x/2x alert).[C]

### 6. Security & Self-Healing
 * **APK Security** — Blocks installation/execution if digital signature is missing, and transitions to L2 Lock state to protect hardware upon detecting repackaging, rooting, or jailbreaking.
 * **Soft Reset (Autonomous Control)** — Chiplet restart, Raft re-election, Token Bucket reset, V-Home re-docking. Permanent isolation upon T-Reg $15\%$ limit and 3 consecutive failures.
 * **Hard Reset (Human Confirmation Required)** — Requires Ed25519 human signature upon entering RECOVERY after releasing Motor EN LOW E_STOP_LATCH (does not aim for self-restart).

### 7. Safety Framework
 * **S-01 Heinrich (1931)** — The 300:29:1 ratio is cited solely as a historical and philosophical motivation; actual implementation is based on Safety-II and Just Culture.
 * **S-02 ~ S-05 & Functional Safety Standards** — Swiss Cheese active blocking, Defense in Depth, Fail-Safe (EN PIN LOW), ALARP expansion, and compliance with ISO 13849-1 Cat 4 PL e / IEC 61508 SIL3 / GDPR Article 5(1)(e) PII $10\text{s}$ destruction clause.

### 8. Prior Art & Disclaimer
 * **Prior Art Registry Listing Specifications (CERN Zenodo DOIs)** —
   * deundeuni/CWP-Battery-Swap (DOI: 10.5281/zenodo.22373538)
   * deundeuni/CWP-Clamping-Battery-Swap-System (DOI: 10.5281/zenodo.22373722)
   * deundeuni/CWP-Rolling-Self-Align-Battery-Swap-System (DOI: 10.5281/zenodo.22373704)
   * deundeuni/LAST-LIGHT (DOI: 10.5281/zenodo.22373189)
   * deundeuni/MAX-LIFE-ICE-BELT (DOI: 10.5281/zenodo.22373686)
   * deundeuni/chiplet-apu-multi-system-survival-architecture (DOI: 10.5281/zenodo.22374987)
     *(The above CERN Zenodo / DataCite global academic registries registration completed / Active)*
 * **Prior Art Registration Notice** — Timestamp records are registered in all commit hashes of this document and CERN Zenodo / DataCite global academic registries. This aims to mitigate third-party private monopoly patent risks and serve as a reference for prior art in the public domain during global patent examinations to help support arguments against lack of novelty and inventive step.
 * **Non-Intentional Omission & Non-Exhaustive Disclaimer** — The technical standards, public domain principles, laws, and related repository lists cited or enumerated in this specification are illustrative descriptions to aid understanding and do not imply comprehensive or rigid limitation. Due to the author's subjective limitations or cognitive errors, the explicit mention of specific detailed specifications, related industry standards, subsequent amendments, or equivalent prior art may have been omitted or cumulatively skipped, but this does not constitute intentional concealment or exclusion. All derivative standards, revised specifications, equivalent mechanisms, and public domain technology combinations connected to the disclosed upper-level technical ideas are considered to be included within the scope of prior art coverage of this defensive publication white paper.

---
origin: by deundeuni | domain: somamoa.ai.kr | repo: github.com/soma-moa | v2.2.1 Revision: 2026-09-17 | PHILOSOPHY.ko.md is authoritative | CC BY 4.0 & DPL
