# soma-moa : Spec v2.2 Final
> **domain:** `somamoa.ai.kr` | **repo:** `github.com/soma-moa`  
> **Initial Record Date:** 2026-08-27 | **Last Revised:** 2026-09-17 | **v2.2 Final (v2.2.1 Patch)**  
> **Status:** English/Korean Technical Standard | **Authoritative:** `PHILOSOPHY.ko.md`  
> **License:** CC BY 4.0 & DPL | **Origin:** by deundeuni (soma-moa)  
> **원본 조항:** 한국어 원문(`PHILOSOPHY.ko.md`)이 기준 원본이며, 번역본은 참고용이다.

---

### 1. 핵심 아키텍처 (Core Architecture)

$$\text{[Brain: LLM/VLM Probabilistic]} \longrightarrow \text{[Governance: soma-moa Deterministic eFPGA]} \longrightarrow \text{[Actuator/APK]}$$

- **L0 Physical —** CWP Battery-Swap (60T/61T Diff) + V-Home Self-Align $\pm 5\text{mm}$ + $0.1\text{ms}$ HW Intercept E-Stop (Motor EN PIN LOW 차단 제어)
- **L1 Compute —** Chiplet-APU Many as One Dual-Redundant + CCS $70\% / 100\text{ms}$ Raft Role-Swapping + 갓길 3중 관제 (Token Bucket + T-Reg $15\%$ + Tri-State)
- **L2 Governance —** Brain vs Governance 물리 분리 + eFPGA $0.1\text{ms}$ Blocker + FSM
  $$\text{IDLE} \longrightarrow \text{MONITOR} \longrightarrow \text{VALIDATE (<0.02ms)} \longrightarrow \text{PRELOCK (80\%)} \longrightarrow \text{Brain-Override} \longrightarrow \text{E\_STOP\_LATCH (<0.1ms)} \longrightarrow \text{RECOVERY}$$
- **L3 Social —** Quiet Assist 1x/2x Haptic + Anonymized Delta Logging PII $10\text{s}$ 자동 삭제 지향 + Just Culture

#### 1.1 엣지 정량 파라미터 및 제약 조건
- **CBOR 데이터 페이로드 —** L0 24B (PII 제거) / L1 32B (8B token 포함), each $< 50\text{B}$ Array Encoding ($0.01\text{mm}$ 양자화)
- **SDK 제약 —** $35.2\text{KB} < 42\text{KB}$ Zero-Dep C/Rust
- **RAM 메모리 —** $3.2\text{KB}$ ($100 \times 32\text{B}$, $10\text{s}$ 휘발성 버퍼)
- **검증 지연시간 —** L0 Sync $0.1\text{ms}$ HMAC HW Bypass / L1 Async $2\sim5\text{ms}$ Ed25519

---

### 1.2 장소 매핑 - 기업/일상/개인 소분류 (Location Mapping & Classification)

- **[A] 기업용 (Enterprise) — 멈추면 안 되는 가동 연속성 중심 환경 (L0/L1/L2 중심)**
  - 물류센터 — 차량번호/도크 배정/안전교육 수록, L0 충돌 $0.1\text{ms}$ 차단 제어, L1 재고조회 연동.
  - 공장/클라우드 팜 — Chiplet-APU Many as One + CCS Raft + $85\%$ 백프레셔 스로틀링 + 백혈구 스캔 격리.
  - 기기 AS센터 (노트북/스마트폰/카메라) — 모델명/시리얼/증상/보증/수리이력/엔지니어 배정 연동. 상주 단말은 일일점검 및 L1진단/L3중개를 수행하며 재가동 권한은 미부여.
  - 백화점/병원 상주 — 반품/분실물/VIP/미아보호/다국어 대응, L1 재고조회 및 L3 에스컬레이션 연동.

- **[B] 일상용 (Daily) — 탐색과 편의 지원 중심 환경 (L3 + Vibe Search 중심)**
  - 푸드코너/식당 — 메뉴/알러지/대기번호/좌석/픽업 호출 및 건강 루틴 연동. 알러지 정보 불확실 시 추측을 지향하지 않고 L3 에스컬레이션 수행.
  - 백화점 서비스센터 방문객 — 분실물/미아보호/다국어 안내 지원.
  - 도서관 사서 Vibe Search — 제목 미인지 시 표지/느낌/줄거리 기반 서적 탐색.
  - 음악 탐색 — 흥얼거림/멜로디/느낌/가사 맥락 탐색. Confidence $90\%$ 미만 시 단정적 추측을 지향하지 않고 L3 연결.

- **[C] 개인용 (Personal) — 프라이버시 존중 및 저소음 환경 (L3 중심)**
  - 개인 커스텀 — 약/할일/건강 루틴, 기기 수리이력/보증, 식단/알러지 관리.
  - 조용한 보조 — 공공 경고음 대신 작업자 본인만 인지하는 햅틱 1x(주의) / 2x(정지) 알림 활용.
  - 기록 없는 배려 — 경미한 실수는 $10\text{s}$ 후 자동 삭제하여 부담을 완화하며, 물리적 위험 항목만 기록 보존 (GDPR 5(1)(e)).

---

### 1.3 유기적 자체 선조치 원칙 (Organic Self-Resolution Principle)

사람이 개입하기 전 현장 내부에서 유기적 연동을 통해 선조치를 완료하는 구조를 지향한다.

$$\text{자체 해결 가능 장애 (오정렬, 과부하, 패킷 버스트)} \longrightarrow \text{L0/L1/L2 내부 선조치 (Token Bucket, Raft, Tri-State, T-Reg)}$$
$$\text{인간 에스컬레이션 (L3)} \longrightarrow \text{최후의 수단으로 유보하여 피로도 최소화}$$

- **L0 자체 해결 —** V-Home $\pm 5\text{mm}$ 물리적 오차 정밀 흡수 재시도, CWP 차동(60T/61T Diff) 저충격 재도킹, $0.1\text{ms}$ E-Stop 후 자체 재인가 시도.
- **L1 자체 해결 —** 큐 $85\%$ 백프레셔 감지 시 스로틀링, CCS $70\%$ Raft $100\text{ms}$ 재선출, 백혈구 격리 버퍼, T-Reg $15\%$ 자원 억제, Tri-State 영구 격리.
- **L2 자체 해결 —** eFPGA $0.02\text{ms}$ VALIDATE $\rightarrow$ $80\%$ PRELOCK $\rightarrow$ Brain-Override $\rightarrow$ E_STOP_LATCH 내부 래치 제어. 클라우드 로그 없이 내부 CBOR 데이터만 보존.

---

### 2. 0번 헌장 (Axiom 0)

*"로봇/AI는 부(Sub), 시스템 거버넌스는 주(Main)지만, 그 거버넌스조차도 인간의 주 작업에는 보조(Auxiliary)다."*  
인간 최종 판단권을 보장하여 "웃으며 출근, 웃으며 퇴근"하는 안전한 공존 환경 조성을 지향한다.

---

### 3. 보안 및 자가치유 (Security & Self-Healing)

Proof-of-Clearance (Ed25519), Cloud-Sign / Edge-Verify, CBOR L0 24B / L1 32B (each $< 50\text{B}$) Array Encoding ($0.01\text{mm}$ 양자화), SDK $35.2\text{KB} < 42\text{KB}$ Zero-Dep C/Rust, RAM $3.2\text{KB}$ ($100 \times 32\text{B}$, $10\text{s}$ 휘발성 버퍼), L0 Sync $0.1\text{ms}$ HMAC HW Bypass / L1 Async $2\sim5\text{ms}$ Ed25519.

#### 3.1 APK 보안 및 무결성
- **서명 검증 및 무결성 제어 —** 전자서명 미보유 시 무결성 검증 실패로 애플리케이션 실행을 차단 제어한다.
- **루팅 및 탈옥 대응 —** 단말의 루팅 또는 탈옥 감지 시 L2 Lock 및 Telemetry 기록을 보존하여 하드웨어 안전을 확보한다.
- **외부 로그 최소화 —** 무단 클라우드 로그 수집을 지향하지 않으며, 내부 CBOR 인코딩 데이터 중심의 로컬 안전 보존 체계를 유지한다.

#### 3.2 자가치유 리셋 구분 (Soft Reset vs Hard Reset)
- **Soft Reset (자율 제어) —** 대상: 칩렛 재기동, Raft 재선출, Token Bucket 리셋, V-Home 재도킹, 백혈구 격리 해제 / 인간 서명: 불요 / 조건: T-Reg $15\%$ 제한 적용, 동일 칩렛 3회 연속 실패 시 Tri-State 영구 격리 / 근거: Safety-II Resilience, Graceful Degradation.
- **Hard Reset (인간 확인 필수) —** 대상: Motor EN LOW E_STOP_LATCH 해제 $\rightarrow$ RECOVERY / 인간 서명: Ed25519 Human Sign-off 필수 (미서명 시 영구 래치 유지 지향) / 조건: 자동 재기동(Self-restart)을 제한하고 수동 승인 복구 지향 / 근거: ISO 13849-1 Cat 4 PL e, IEC 61508 SIL3 Fail-Safe.

---

### 4. 에스컬레이션 및 운영 체계 (Escalation & Operations)

$$\text{L1 (BLE/MQTT-SN 햅틱 1x/2x)} \longrightarrow \text{L2 (Lock \& Telemetry 위험 기록)} \longrightarrow \text{L3 (WebRTC Sign-off 인간 승인)}$$

- **4.1 AS 3종 체계 —** 원격/OTA 지원, 출동 서비스, 상주 서비스 (병원/공장/백화점/물류/AS센터/푸드코너). 상주 직원은 단순 재가동 권한이 없으며 판단 대신 규격 집행만 수행.
- **4.2 자체 선조치와 에스컬레이션 관계 —** 자체 선조치 실패 카운트 3회 도달 또는 T-Reg/Tri-State 임계 초과시에만 L3 에스컬레이션을 발동하여 인간의 관리 피로도를 최우선으로 낮춘다 (Quiet Assist).

---

### 5. 안전 프레임워크 및 정량 규격 (Safety Framework & Standards)

- **[S-01] Heinrich 1931 (300:29:1) —** 역사적·철학적 동기로 원용하며, 실제 구현은 Safety-II, Just Culture, 익명 근접보고 체계에 기반.
- **[S-02] Swiss Cheese (Reason 1990) —** 방어선 결함 능동 차단 및 완화.
- **[S-03] Defense in Depth —** 계층별 다중 방어 체계.
- **[S-04] Fail-Safe —** Motor EN PIN LOW 물리적 신호 차단 제어.
- **[S-05] ALARP 확장 및 규격 준수 —** ISO 13849-1 Cat 4 PL e, IEC 61508 SIL3, GDPR Article 5(1)(e) PII $10\text{s}$ 자동 삭제 지향.

#### 5.1 최신 안전 상식 적용
- **Safety-II (Hollnagel) —** 사고 1건의 예방뿐만 아니라 정상적으로 작동하는 $9,999$건의 연속성을 안정적으로 유지하는 데 집중 (Many as One + Raft 구현).
- **Just Culture —** 가벼운 실수는 $10\text{s}$ 후 삭제하고 익명 CBOR 로깅을 통해 사고 징후 보고를 자율화.
- **스위스 치즈 능동화 —** 백혈구 스캔, T-Reg $15\%$, Tri-State 절단을 통해 방어선 구멍 형성을 사전 완화.

---

### 6. Article X 및 확장 인터페이스 (Article X & Extended Interfaces)

- **Article X —** 하드웨어 섀시(바퀴/4족/휴머노이드) 형태와 무관하게 I/O 2대 요건으로 통제. Brain(AI)은 제안만 수행하며 Governance가 결정론적 최종 집행.
- **6.1 Vibe Search —** 도서관 서적 탐색(표지/느낌/줄거리) 및 음악 흥얼검색(멜로디/느낌/가사) 연동. Confidence $90\%$ 미만 시 단정적 추측을 지향하지 않고 L3 에스컬레이션 수행.

---

### 7. 규격 검증 및 표준 인용 (Specification Verification & Standards)

- **통신 및 합의 표준 —** CBOR RFC 8949, Raft Ongaro 2014, HMAC-SHA256, Ed25519 RFC 8032.
- **기능안전 및 법률 준수 —** ISO 13849-1:2023 PL e, IEC 61508 SIL3, GDPR 5(1)(e), USPTO AI Inventorship Guidance (2024.02), Thaler v. Vidal (2022), EPO G-II 3.3.1.

---

### 8. 개방형 기반 모델 및 독자 창작 출처 (Open Models & Attribution)

본 프로토콜은 1인 설계자(`deundeuni`)의 공장 기계 샘플 작업 및 건설 현장 노동 경험에서 도출된 일상적 사유에서 출발했다.

이 설계 체계화 과정에서 개방형 AI 모델(대규모 언어 모델 등)을 기술 교차 검증, 수치 검수 및 표준 서식 구조화 보조 도구(Drafting & Verification Tool)로 활용했다. 개방형 AI 모델은 문서화 보조 수단이며, 본 기술의 핵심 착상(Conception) 및 독자적 아키텍처 설계 주권은 `deundeuni`에게 있다 (USPTO 2024 AI Inventorship Guidance 준수).

영업비밀인 eFPGA RTL 코드, 정밀 CAD 도면, 펌웨어 바이너리 소스는 비공개 유지를 원칙으로 한다.

---

### 9. 선행기술 등록 및 수치 가이드라인 면책 고지 (Prior Art & Disclaimer)

- **선행기술 글로벌 레지스트리 등재 명세 (Zenodo DOIs / GitHub Repositories) —**
  - `deundeuni/CWP-Battery-Swap` (DOI: `10.5281/zenodo.22373538`)
  - `deundeuni/CWP-Clamping-Battery-Swap-System` (DOI: `10.5281/zenodo.22373722`)
  - `deundeuni/CWP-Rolling-Self-Align-Battery-Swap-System` (DOI: `10.5281/zenodo.22373704`)
  - `deundeuni/LAST-LIGHT` (DOI: `10.5281/zenodo.22373189`)
  - `deundeuni/MAX-LIFE-ICE-BELT` (DOI: `10.5281/zenodo.22373686`)
  - `deundeuni/chiplet-apu-multi-system-survival-architecture` (DOI: `10.5281/zenodo.22374987`)
  *(상기 CERN Zenodo / DataCite 글로벌 학술 레지스트리 등재 완료 / Active)*

- **수치 가이드라인 선언 및 상업적 보증 불용 고지 (Target Figures & AS-IS Disclaimer) —** 본 명세서에 기재된 모든 정량 수치(시간, 응답 지연, 임계치, 용량 파라미터 등)는 시스템 최고 생존력을 지향하는 **목표치 가이드라인(Target Figures)**이며 상업적 동작 완전성을 보증하지 않는다 (Provided AS-IS). 실제 산업 현장 구현 시 관련 안전 표준 및 현장 조건에 맞춘 전문 엔지니어의 재검증이 필수적으로 요구된다.

- **비의도적 생략 및 예시적 미한정 고지 —** 명세서상 인용 표준 및 관련 저장소 목록은 이해를 돕기 위한 예시적 서술이며 전면적 한정을 의미하지 않는다. 작성자의 주관적 한계로 누락된 파생 개정 규격 및 균등 공지기술은 본 방어적 공개 백서의 선행기술 포괄 범주에 포함된 것으로 간주한다.

---
origin: by deundeuni (soma-moa) | domain: somamoa.ai.kr / Somamoa.ai.kr | repo: github.com/soma-moa
Initial: 2026-08-27 | Revised: 2026-09-17 | v2.2 Final (v2.2.1 Patch) | PHILOSOPHY.ko.md is authoritative | License: CC BY 4.0 & DPL
