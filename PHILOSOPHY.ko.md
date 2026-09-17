# soma-moa : Design Philosophy & Prior Art Declaration
> **original design:** `deundeuni (soma-moa)` | **repository:** `github.com/soma-moa`  
> **initial record date:** 2026-08-24 | **prior art declaration:** 2026-08-25 | **v2.2.1 Revision:** 2026-09-17  
> **domain:** `somamoa.ai.kr` | **License:** CC BY 4.0 & DPL  
> **네이밍 사전 정의:** 오픈소스 프로토콜 및 코드베이스 표기는 `soma-moa`(소문자 하이픈), 서비스 브랜드 및 프로젝트 대표 명칭은 `Somamoa`를 사용하며 동일 정체성을 지닌다.  
> **원본 조항:** 한국어 원문(PHILOSOPHY.ko.md)이 기준 원본이며, 번역본은 참고용이다.

이 문서는 `soma-moa`가 왜 이렇게 설계되었는가에 대한 기록이다.  
결과가 아니라 과정, 스펙이 아니라 사유의 흔적이다.

---

### 0. 모국어로 시작한 설계

soma-moa는 영어로 먼저 만들고 한국어로 번역한 기술이 아니다.  
원래는 공장에서 다양한 기계를 만지며 샘플 작업을 하고, 건설노동자로 일하며 일상에서 쌓인 지식으로 시작했다. 최근 AI를 알게 되면서 '이것도 자료를 만들 수 있지 않을까'에서 출발한 기록이다.

한국어로 깊게 사유하고, 그 사유를 글로벌 규격 코드로 증명한 프로토콜이다.  
그래서 `moa(모아)`는 별칭이 아니라 본명이다.

영어 gather, collect는 "모은다"로 번역되지만, "파편화된 에러 로그와 분산된 단말을 한데 보듬어 모은다"는 온도는 한국어 '모아'에만 담겨 있다.

이것이 soma-moa의 정체성이자 설계의 시작점이다.

**독립적 선행 연구 및 무독점 고지 (Modesty & Non-Exclusivity Notice):**  
본 프로토콜은 1인 설계자의 일상 및 현장 경험과 사유에서 구상되었으나, 유사한 기술적 사상이나 아이디어가 타 연구자에 의해 독립적으로 선행 연구되었을 가능성을 배제하지 않는다. 본 문서는 특정 주체의 배타적 독점을 방지하고, 공공의 선행기술(Prior Art)로서 누구나 자유롭게 참조 및 발전시킬 수 있도록 무상 공개된다.

---

### 1. v0.1 OSRP - 뼈대만 있던 시절

**프로젝트명: OSRP (Open Symbiotic Routine Protocol)**

처음엔 기본 뼈대부터 잡았다.
- **제로 트러스트 보안:** 승인망만 연결을 허용하고, 센서 데이터는 내부망으로 직행을 지향한다.
- **3단계 에스컬레이션:** WebRTC 화상 -> Telemetry 로그 -> 사람이 직접 출동한다.
- **인간 최종 통제권:** 로봇이 단독으로 결정하는 상황을 통제하고 인간 개입권을 보장한다.

'Routine'이라는 단어는 단순 스케줄러처럼 보여 폐기했다. 엔지니어링 약어로서 직관성이 떨어진다는 점도 반영했다.

---

### 2. v1.0 SOMA - 몸을 입다

**프로젝트명: SOMA (Symbiotic Operations & Machine Architecture)**

가상 AI가 현실의 몸(그리스어 Soma)을 입는 순간 필요한 거버넌스로 체급을 키웠다.

- **설계 구조:** 하드웨어 섀시(바퀴, 4족, 휴머노이드)의 형태와 무관하게 상위에서 안전과 통제를 담당하는 거버넌스 레이어로 분리.
- **0번 헌장(Axiom 0) 제정:**  
  *"로봇/AI는 부(Sub), 시스템 거버넌스는 주(Main)지만, 그 거버넌스조차도 인간의 주 작업에는 보조(Auxiliary)다."*

---

### 3. v1.5 네이밍 탐색 - 20개의 이름을 지난 기준

SOMA라는 영문명 외에, 발음하기 편하고 직관적인 이름을 찾아 20개 넘게 검토했다.

- **보듬, 결, 이룸** — 발음이 다소 무겁다.
- **누리, 미소, 우리** — 기술적 정체성이 명확히 전달되지 않는다.
- **고리, 다리, 사이** — N:1로 수집하는 플랫폼 전체를 담기엔 범위가 한정적이다.

**정립한 기준 3가지:**
1. 0.1초 만에 발음할 수 있을 것
2. 들었을 때 동작 구조가 그려질 것
3. 분산된 단말을 하나로 모으는 확장성을 담을 것

---

### 4. v2.0 soma-moa - 이름과 표기의 완성

**공식 명칭: soma-moa by deundeuni**

- **moa(모아):** 흩어진 에러 로그와 규격을 한데 모으는 본질.
- **언어적 대칭:** S O M A (ㅗㅏ) - m o a (ㅗㅏ)의 시각적·청각적 운율 일치.
- **소문자 확정:** 개발자가 코드베이스에서 편하게 불러다 쓰는 오픈소스 프로토콜의 정체성을 위해 `soma-moa` 소문자 하이픈 표기로 최종 확정.

---

### 4-1. v2.2 Final - 4층 생존 아키텍처 및 L2 FSM 명세

v2.0의 이름 위에 v2.2에서 시스템의 기본 뼈대가 확정되었다.

- **L0 Physical:** CWP Battery-Swap + V-Home Self-Align + 0.1ms Hardware Intercept E-Stop (Motor EN PIN LOW 차단 제어 지향)
- **L1 Compute:** Chiplet-APU Many as One Dual-Redundant + CCS 70%/100ms Raft Role-Swapping + 갓길 3중 관제
- **L2 Governance:** Brain(Probabilistic) vs Governance(Deterministic) 물리 분리 + eFPGA 0.1ms Blocker + FSM
- **L3 Social:** Quiet Assist Haptic 1x/2x + Anonymized Delta Logging PII 10초 파기

**엣지 검증 파라미터 (Target Design Benchmarks):** CBOR L0 24B + L1 33B <50B, SDK 35.2KB <42KB, RAM 3.2KB <10MB, L0 Sync 0.1ms HMAC HW Bypass / L1 Async 2~5ms Ed25519

**L2 FSM 전이 조건 및 역할 정의:**
- **IDLE:** 정상 대기 상태
- **MONITOR:** 엣지 센서 및 로그 실시간 감시
- **VALIDATE(<0.02ms):** eFPGA 기반 결정론적 안전 규칙 검증
- **PRELOCK(80%):** 위험 예측 확률 80% 도달 시 선제적 하드웨어 잠금 준비
- **OVERRIDE:** AI 추론(Brain)의 이상 제어 시도를 L2 결정론적 거버넌스 및 인간 제어권이 물리적으로 즉시 무효화하고 우위권을 확보하는 단계
- **E_STOP_LATCH(<0.1ms):** 0.1ms 이내 모터 전원 차단 래치 고정
- **RECOVERY:** Ed25519 인간 서명 승인 없이는 복구를 불허하며 영구 래치 상태 유지

---

### 4-2. v2.2 확장 - 일상에서 현장까지

- **AS 3종:** 원격/OTA, 출동, 상주(병원/공장/백화점/물류/수리센터/푸드코너)
- **개인 커스텀:** 약/할일/건강 루틴, 기기 수리이력/보증, 식단/알러지
- **확장 탐색:** 도서관 사서(표지/느낌/줄거리로 책 찾기) + 음악 탐색(흥얼거림/느낌/가사로 찾기)

---

### 4-3. v2.2 소분류 - 기업/일상/개인으로 모아

`moa`는 다 모으지만, 쓰임은 나눠야 가볍다. 그래서 3분류로 소분류했다.

- **기업용(Enterprise):** 가동 연속성이 중요한 운영 환경. 공장, 물류, 병원, AS센터 상주. L0 0.1ms 차단 제어 지향 + L1 Many as One + L2 결정론적 집행 중심. 인간의 최종 판단을 보장.
- **일상용(Daily):** 탐색과 지원이 필요한 환경. 푸드코너, 백화점 서비스센터, 도서관, 음악. Vibe Search + L3 에스컬레이션 중심. 신뢰도 90% 미만 시 단정적 추측 지양.
- **개인용(Personal):** 개인의 영역을 존중하는 환경. 약/할일/건강, 식단/알러지, 수리이력. PII 10초 파기 + 햅틱 1회/2회 + 무분별한 기록 최소화 지향.

다 연결하되, 부담을 분산하는 것이 `보조(Auxiliary)`의 원칙이다.

---

### 4-4. 안전 철학의 계승 - 하인리히는 기본 철학으로만

하인리히 300:29:1은 1931년 제정된 철학적 기틀이다. 비율 자체를 절대적 수치로 한정하기보다 왜 예방 조치를 모아야 하는가에 대한 동기로 원용한다.

실제 구현은 최신 안전 프레임워크에 기반하여 확장 적용한다:
- **Safety-II / Resilience (Hollnagel):** 사고 예방뿐만 아니라 정상적으로 작동하는 9,999건의 상태를 안정적으로 유지하는 데 집중. Many as One과 Raft 기반 아키텍처로 구현.
- **Just Culture + 익명 보고:** 자율적 보고 문화 조성을 위해 CBOR 24B 익명 로깅 + PII 10초 파기 + 경미한 항목 기록 최소화 체계 적용.
- **스위스 치즈 모델의 능동화:** 방어선 누출 위험을 능동적으로 감지하여 백혈구 스캔, T-Reg 15%, Tri-State 절단을 통해 결함을 사전 완화 지향.
- **정량 표준 정립:** 하인리히 비율 대신 ISO 13849-1 Cat 4 PL e / IEC 61508 SIL3 / GDPR 5(1)(e) 등 정식 규격 지표 원용.

> [S-01] Heinrich 1931은 역사적·철학적 동기로 원용하며, 실제 구현은 Safety-II, Just Culture, 결정론적 제어와 익명 근접보고 체계에 기반한다.

---

### 4-5. 유기적 연동과 자체 선조치 철학

현장 내부에서 유기적 연동을 통해 선조치를 완료하는 구조를 지향한다.

- L0에서 V-Home이 ±5mm 범위의 물리적 오차를 정밀 흡수
- L1에서 70% Raft 재선출, 85% 백프레셔, 백혈구 격리를 통해 패브릭 내부 해결 지향
- L2에서 eFPGA가 0.02ms VALIDATE로 잠금 제어를 수행하고 내부 로그 기록

자체 해결이 어려운 상황에 한해 L3에서 햅틱 1회/2회 통지 후 WebRTC를 통한 인간 관리자 연계를 수행하며, 인간 판단의 최후 유보를 통해 기술자의 존엄성을 보호한다.

---

### 4-6. 정량 핵심 스펙 명세 (System Specification Summary)

선행기술 대조 및 심사 정합성을 위한 계층별 주요 정량 파라미터 종합 명세(Target Design Benchmarks)는 다음과 같다.

- **L0 Physical 지연시간 —** 0.1ms Hardware Intercept E-Stop 차단 제어 지향 (Motor EN PIN LOW)
- **L0 물리 오차 흡수 —** V-Home Self-Align ±5mm 정밀 흡수
- **L0/L1 검증 지연시간 —** L0 Sync 0.1ms HMAC HW Bypass / L1 Async 2~5ms Ed25519
- **L1 Compute 합의 임계치 —** CCS Raft 70% 동의 / 100ms Role-Swapping
- **L1 Compute 백프레셔 —** 패브릭 내부 85% 백프레셔 감지 시 자동 스로틀링
- **L1 Compute 데이터 페이로드 —** CBOR 패킷 L0 24B + L1 33B (<50B 이내 제한)
- **L2 Governance 검증 지연 —** eFPGA 결정론적 VALIDATE <0.02ms
- **L2 Governance 예측 임계치 —** PRELOCK 80% 위험 확률 도달 시 선제 차단 준비
- **L2 Governance 자가치유 제약 —** T-Reg 15% 제한 및 3회 실패 시 영구 격리
- **L3 Social 신뢰도 임계치 —** Daily Vibe Search 신뢰도 90% 미만 시 추측 금지
- **L3 Social PII 파기 주기 —** Anonymized Delta Logging 10초 이내 파기
- **Edge 임베디드 리소스 제약 —** SDK 크기 35.2KB (<42KB), RAM 3.2KB (<10MB)

---

### 5. 보조 거버넌스(Auxiliary Governance) & 선행기술 공개 (Prior Art)

**공개 목적 (2026-08-25):** 본 문서는 AI·로봇·인간의 공존을 위한 최소 안전 보조 규격을 선행기술로 공개하여, 특정 주체의 배타적 특허 독점 위험을 완화하고 누구나 활용할 수 있는 공공의 기술로 정립하는 것을 지향한다.

- **공존의 전제:** "웃으며 출근, 웃으며 퇴근"
- **보조의 원칙:** 거버넌스는 주 작업을 방해하지 않는 가벼운 보조 역할 수행
- **결정론적 제어:** AI 이상 동작 감지 시에도 L0 차단기를 통한 전원 버스 차단 제어 지향

---

### 5-1. 기술자 존엄 및 조용한 보조 프로토콜 (Technician Dignity & Quiet Assist Protocol)

- **조용한 보조:** 과도한 경보음 대신 작업자 본인만 인지 가능한 햅틱 1회/2회 알림 활용
- **기록 없는 배려:** 경미한 단순 실수는 10초 후 자동 삭제를 통해 부담을 완화하며, 물리적 위험 항목은 기록을 유지
- **기술자 대우 원칙:** 감시 목적이 아닌 보조자(Auxiliary)로서의 가치 정립

**요약:** 물리적 안전은 L0 차단 제어로 명확히 확보하고, 사회적 안전은 진동 알림과 자율 삭제 조항을 통해 부드럽게 구현한다.

---

### 5-2. 자가치유 리셋 철학 - Soft vs Hard

- **Soft Reset (자율 제어, 인간 서명 불요):** L0/L1 자가치유 — 칩렛 재기동, Raft 재선출, Token Bucket 리셋, V-Home 재도킹. T-Reg 15% 제한 및 3회 연속 실패 시 영구 격리 조건 하에 자율 수행.
- **Hard Reset (인간 확인 필수):** L2 E_STOP_LATCH 해제. Motor EN LOW 래치 해제 후 RECOVERY 단계는 Ed25519 기반 인간 서명 필수 적용. 자동 재기동을 지양하고 ISO 13849-1 / IEC 61508 규격을 준수.

---

### 6. 기술 작성 지원 및 법리적 주체 명시 (Technical Drafting Support & Legal Doctrine)

- **Technical & Legal Drafting Support:** Generic Generative AI Text Refinement & Structuring Tools (범용 생성형 AI 텍스트 정제 및 구조화 도구)
- **역할 및 IP 귀속 고지:** 본 문서는 범용 생성형 AI 텍스트 정제 및 구조화 도구를 활용하여 기술 문맥의 구조화, 검수 및 표현 완화 보조를 수행하였다. 본 고지는 역할 투명성을 위한 것이며, AI 프롬프트 및 내부 추론 과정은 공개하지 않는다. 모든 핵심 기술 착상(Conception), 시스템 독자 아키텍처 설계, 최종 결정 및 지식재산권(IP) 소유권은 원안자(deundeuni / soma-moa)에게 전적으로 귀속된다.
- **법리적 원용 (USPTO / EPO / 판례):** AI 발명자성을 인정하지 않는 미국 대법원/CAFC 판례(*Thaler v. Vidal*), USPTO AI 발명 자격 가이던스(2024.02), EPO 심사지침(G-II 3.3.1)을 원용한다. 범용 AI 도구는 기술 문서 정제 보조 수단일 뿐이며, 본 기술 체계의 독자적 착상 주체는 인간 설계자(deundeuni)임을 법리적으로 확정한다.
- **규격 준수:** ISO 13849-1 Cat 4 / PL e, IEC 61508 SIL3, GDPR 5(1)(e) 표준 준수 지향.

---

### 7. 실리보호 및 Somamoa 브랜드 확장 (Defensive Rights & Brand)

- **오픈소스 프로토콜 코드명:** `soma-moa`
- **공식 프로젝트 및 브랜드명:** `Somamoa`
- **공식 도메인:** `somamoa.ai.kr` / `Somamoa.ai.kr`
- **실리보호 및 방어적 공개:** 본 프로토콜의 기술적 구성 및 사상은 선행기술로 무상 공개되며, 타 주체의 무단 특허화로부터 공공 영역의 범주를 넓혀 기술 생태계를 보호하는 것을 지향한다.

---

### 8. 개방된 기반 모델과 1인 설계 및 출처 (Conception & Attribution)

본 프로토콜은 1인 설계자(deundeuni)의 사유에서 출발했다. 공장에서 기계를 다루며 샘플 작업을 수행하고, 건설노동자로서 현장에 참여하며 축적된 실제 일상의 지식에서 시작되었다.

soma-moa는 이러한 현장 사유를 글로벌 규격 코드로 체계화한 선행기술 기록이다.

이 설계 체계화 과정에서 트랜스포머 아키텍처 및 개방된 기술 기반과 함께 범용 AI 문맥 정제 도구를 검토 보조 수단으로 활용하였다. 모든 핵심 착상 및 독자적 아키텍처 설계의 법리적·기술적 주체는 deundeuni에게 있다.

---

### 9. 출처 및 선행기술 근거 (Sources)

- **안전 이론:** Heinrich (1931) 300/29/1 — 철학적 동기, Reason (1990) Swiss Cheese, Hollnagel Safety-II/Resilience, Defense in Depth, Fail-Safe, ALARP, Just Culture
- **기능안전:** ISO 13849-1:2023 PL e, IEC 61508 SIL3, GDPR Article 5(1)(e)
- **통신/합의:** RFC 8949 CBOR, Ongaro 2014 Raft, HMAC-SHA256, Ed25519 RFC8032
- **법률:** USPTO AI Inventorship Guidance 2024.02, Thaler v. Vidal 2022, EPO G-II 3.3.1
- **검증 및 문서 작성 도구:** Generic Generative AI Text Refinement & Structuring Tools (Conception by deundeuni)
- **영업비밀:** eFPGA RTL, 정밀 CAD, 펌웨어 바이너리는 비공개 유지

---

### 10. 변경 이력 및 정합화 패치 기록 (Revision History)

- **v2.2.1 (2026-09-17):**
  - **독립 선행 연구 및 무독점 고지 신설 (0장):** POLYLINK-HUD 0.9항 취지를 원용하여 공공 선행기술화 및 겸양 고지 명시.
  - **기술 작성 지원 및 법리적 주체 명시 일반화 (6장, 8장, 9장):** 특정 AI 기업 실명 제거 및 v3.6 Appendix C 표준 문구 적용, Sole Invention(deundeuni) 법리적 귀속 재확인.
  - **Target Design Benchmarks 톤 보정 (4-1장, 4-6장):** 정량 스펙을 목표 설계 벤치마크로 명확히 하고 지향적 표현 정비.
- **v2.2 Final (2026-08-27):** 4층 생존 아키텍처(L0~L3) 및 L2 FSM 명세 확정, 소분류(기업/일상/개인) 적용.
- **v2.0 (2026-08-25):** 선행기술 방어적 무상 공개 선언, `soma-moa` 소문자 하이픈 명칭 확정.
- **v1.0 / v0.1 (2026-08-24):** SOMA 및 OSRP 초기 거버넌스 아키텍처 기획.

---
origin: by deundeuni (soma-moa) - factory sample work & construction worker background  
domain: somamoa.ai.kr / Somamoa.ai.kr | repo: github.com/soma-moa  
Zenodo DOI: 10.5281/zenodo.22373538 / 22373722 / 22373704 / 22373189 / 22373686 / 22374987 (등재 완료 / Active)  
prior art: 2026-08-25 | v2.2.1 Revision: 2026-09-17 | License: CC BY 4.0 & DPL
