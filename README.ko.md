# soma-moa : Human-Centered Physical AI & Spatial Governance Protocol
> **original design:** `deundeuni (soma-moa)` | **repository:** `github.com/soma-moa`  
> **domain:** `somamoa.ai.kr` | **v2.2.1 Revision:** 2026-09-17 | **License:** CC BY 4.0 & DPL  
> **문서 상태:** 한국어 원문(README.ko.md / PHILOSOPHY.ko.md)이 기준 원본이며, 번역본은 참고용이다.

### 0. 정의 (Definition)
soma-moa는 일상에서 시작되어 병원, 공장, 빌딩 로비, 백화점 서비스센터, 물류센터, 기기 AS센터(노트북/스마트폰/카메라), 푸드코너/식당 무인 비서 등 다양한 현장으로 확장되는 방문 안내 및 공간 보조 비서 로봇 프로토콜이다.

### 1. 0번 헌장 (Axiom 0)
"로봇/AI는 부(Sub), 시스템 거버넌스는 주(Main)지만, 그 거버넌스조차도 인간의 주 작업에는 보조(Auxiliary)다."

### 2. 핵심 아키텍처 (Core Architecture)
$$\text{[Brain]} \longrightarrow \text{[Governance: soma-moa eFPGA]} \longrightarrow \text{[Actuator/APK]}$$
 * **Article X 규격** — 바퀴, 4족, 휴머노이드, 키오스크, 홀로그램, 스노우볼 형태 등 하드웨어 섀시 구조와 무관하게 상위 I/O 2대 요건으로 동일 통합 통제를 지향한다.

### 3. 4층 생존 아키텍처 (4-Layer Survival System)
 * **L0 Physical** — CWP 배터리 교환 + V홈 Self-Align $\pm 5\text{mm}$ + $0.1\text{ms}$ 물리 차단선 E-Stop (Motor EN PIN LOW 차단 제어)
 * **L1 Compute** — Chiplet-APU Many as One 이중화 + CCS $70\% / 100\text{ms}$ Raft 무중단 역할 교체 + 갓길 3중 관제 (Token Bucket + T-Reg $15\%$ + Tri-State)
 * **L2 Governance** — Brain(확률) vs Governance(결정론) 물리 분리 + eFPGA $0.1\text{ms}$ Deterministic Blocker
 * **L3 Social** — Quiet Assist 햅틱 1회/2회 + Anonymized Delta Logging PII $10\text{s}$ 자동 삭제 지향

### 4. 엣지 검증 (Edge Verification)
 * **CBOR 페이로드 예시** — 직렬화 및 메모리 패딩 포함 기준 각각 $< 50\text{B}$ 이내 지향 (L0 $\sim 24\text{B}$ PII 제거, L1 $\sim 32\text{B}$ 8B 토큰) ($0.01\text{mm}$ 양자화)
 * **임베디드 제약** — SDK 크기 $35.2\text{KB} < 42\text{KB}$ Zero-Dep C/Rust, RAM $3.2\text{KB}$ (32B $\times$ 100 Logs 기준)
 * **동기/비동기 지연시간** — L0 Sync $0.1\text{ms}$ HMAC 하드웨어 Bypass / L1 Async $2\sim5\text{ms}$ Ed25519

```rust
// 구조체 크기는 Rust 컴파일러의 #[repr(C)] 메모리 레이아웃 패딩을 포함한 목표(Target) 예시값임.
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

### 5. 장소 매핑 (Location Mapping)
 * **기업용 (Enterprise)** — 물류센터, 공장, AS센터, 백화점/병원 상주 등 가동 연속성 중심 환경 (상주 단말 재가동 권한 미부여).[A]
 * **일상용 (Daily)** — 푸드코너, 도서관, 음악 탐색 등 Vibe Search 중심 환경 (신뢰도 $90\%$ 미만 시 단정적 추측 지향 안 함).[B]
 * **개인용 (Personal)** — 약/할일/건강/식단/수리이력 등 개인화 환경 (PII $10\text{s}$ 파기 + 햅틱 1x/2x 알림).[C]

### 6. 보안 및 자가치유 (Security & Self-Healing)
 * **APK 보안** — 전자서명 미보유 시 설치/실행을 차단 제어하며, 리패키징, 루팅, 탈옥 감지 시 L2 Lock 상태로 전환되어 하드웨어를 보호한다.
 * **Soft Reset (자율 제어)** — 칩렛 재기동, Raft 재선출, Token Bucket 리셋, V-Home 재도킹. T-Reg $15\%$ 제한 및 3회 연속 실패 시 영구 격리.
 * **Hard Reset (인간 확인 필수)** — Motor EN LOW E_STOP_LATCH 해제 후 RECOVERY 진입 시 Ed25519 인간 서명 필수 (Self-restart 지향 안 함).

### 7. 안전 프레임워크 (Safety Framework)
 * **S-01 Heinrich (1931)** — 300:29:1 비율은 역사적·철학적 동기로 원용하며, 실제 구현은 Safety-II 및 Just Culture에 기반한다.
 * **S-02 ~ S-05 및 기능안전 규격** — Swiss Cheese 능동 차단, Defense in Depth, Fail-Safe (EN PIN LOW), ALARP 확장 및 ISO 13849-1 Cat 4 PL e / IEC 61508 SIL3 / GDPR Article 5(1)(e) PII $10\text{s}$ 파기 조항을 준수한다.

### 8. 선행기술 등록 및 고지 (Prior Art & Disclaimer)
 * **선행기술 레지스트리 등재 명세 (CERN Zenodo DOIs)** —
   * deundeuni/CWP-Battery-Swap (DOI: 10.5281/zenodo.22373538)
   * deundeuni/CWP-Clamping-Battery-Swap-System (DOI: 10.5281/zenodo.22373722)
   * deundeuni/CWP-Rolling-Self-Align-Battery-Swap-System (DOI: 10.5281/zenodo.22373704)
   * deundeuni/LAST-LIGHT (DOI: 10.5281/zenodo.22373189)
   * deundeuni/MAX-LIFE-ICE-BELT (DOI: 10.5281/zenodo.22373686)
   * deundeuni/chiplet-apu-multi-system-survival-architecture (DOI: 10.5281/zenodo.22374987)
     *(상기 CERN Zenodo / DataCite 글로벌 학술 레지스트리 등재 완료 / Active)*
 * **선행기술 등록 고지** — 본 문서의 모든 커밋 해시(Commit Hash) 및 CERN Zenodo / DataCite 글로벌 학술 레지스트리에 타임스탬프 기록이 등재되어 있습니다. 이는 제3자의 사적 독점 특허화 위험을 완화하고, 전 세계 특허 심사 시 공공 영역의 선행기술(Prior Art)로 참조되어 신규성 및 진보성 논박 근거로 활용 가능하도록 돕는 것을 지향합니다.
 * **비의도적 생략 및 예시적 미한정 고지 (Non-Intentional Omission & Non-Exhaustive Disclaimer)** — 본 명세서에 인용되거나 열거된 기술 표준, 공지 원리, 법령 및 관련 저장소 목록은 이해를 돕기 위한 예시적 서술이며 전면적·고착적 한정을 의미하지 않습니다. 작성자의 주관적 한계나 인지적 착오로 인해 특정 세부 규격, 관련 산업 표준, 후속 개정안 또는 균등 선행기술의 명시가 누락되거나 누적 생략되었을 수 있으나, 이는 의도적인 은폐나 배척이 아닙니다. 개시된 상위 기술 사상과 연결되는 모든 파생 표준, 개정 규격, 균등 기구 및 공지기술 조합은 본 방어적 공개 백서의 선행기술 포괄 범주에 포함된 것으로 간주합니다.

---
origin: by deundeuni | domain: somamoa.ai.kr | repo: github.com/soma-moa | v2.2.1 Revision: 2026-09-17 | PHILOSOPHY.ko.md is authoritative | CC BY 4.0 & DPL
