<div align="center">

# Toolgate

### 업무를 설명하면, 쓸 수 있는 도구를 찾습니다.

**사내 SaaS · 생성형 AI 도구 보안 사전점검 및 도입 셀프서비스 플랫폼**

임직원은 하려는 업무를 자연어로 설명하기만 하면 됩니다.<br/>
데이터 민감도 판정, 사내 보안정책 대조, 유휴 라이선스 확인까지 시스템이 한 흐름으로 처리합니다.

<br/>

![Spring Boot](https://img.shields.io/badge/Spring%20Boot-6DB33F?style=flat-square&logo=springboot&logoColor=white)
![Spring Cloud](https://img.shields.io/badge/Spring%20Cloud-6DB33F?style=flat-square&logo=spring&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)
![Vue 3](https://img.shields.io/badge/Vue%203-4FC08D?style=flat-square&logo=vuedotjs&logoColor=white)
![Kafka](https://img.shields.io/badge/Apache%20Kafka-231F20?style=flat-square&logo=apachekafka&logoColor=white)
![MariaDB](https://img.shields.io/badge/MariaDB-003545?style=flat-square&logo=mariadb&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)

<br/>

<img src="assets/sc03-result-approved.png" width="900" alt="Toolgate 사전 점검 결과 화면" />

<br/>

**[→ In-house SaaS Security Pre-inspection Platform 저장소 바로가기](https://github.com/5jo-s/In-house-SaaS-Security-Pre-inspection-Platform)**

</div>

<br/>

## 왜 만들었나

SaaS와 생성형 AI 도구가 부서 단위로 빠르게 도입되면서, 기업은 **쓰지 않는 라이선스에 돈을 내는 문제**와 **승인되지 않은 도구로 데이터가 새는 문제**를 동시에 겪고 있습니다.

| 구분 | 확인된 수치 | 출처 |
| --- | --- | --- |
| 미사용 라이선스 지출 | NASA, 5년간 미사용 오라클 라이선스에 **약 1,500만 달러** 지출 | NASA OIG `IG-23-008` (2023-01) |
| 미승인 AI 도구 유출 | 삼성전자 DS 부문, **20일 만에 3건**의 사내 자료가 ChatGPT에 입력 | Bloomberg (2023-05) |
| 라이선스 미사용률 | 기업 보유 SaaS 라이선스의 **평균 36%가 미사용** 상태 | Zylo, 2026 SaaS Management Index |

> **한 줄 문제 정의**<br/>
> 사내 SaaS 툴 정보와 도입 프로세스의 파편화로 인해, 임직원의 탐색 비용이 증가하고 관리자의 중복 검토 및 불필요한 라이선스 구매 등 리소스 낭비가 발생한다.

<br/>

## 무엇이 다른가

기존 SaaS 관리 솔루션이 **관리자 관점의 자산·사용량·비용 관리**에 집중한다면, Toolgate는 **임직원의 업무 요구**에서 출발합니다.

| | 기존 방식 | Toolgate |
| --- | --- | --- |
| **시작점** | 도구 이름을 알아야 신청 가능 | 업무 목적을 자연어로 설명 |
| **데이터 등급** | 사용자가 직접 선택 | 업무 설명에서 시스템이 추론 |
| **보안 판정** | 담당자가 규정을 찾아 수기 검토 | 사내 정책 문서 RAG 검색 → 근거와 함께 자동 판정 |
| **구매 요청** | 보유 자산 확인 없이 신규 구매 | 유휴 라이선스를 먼저 제안, 없을 때만 구매 검토 |
| **검토 큐** | 저위험·고위험 요청이 한 큐에 혼재 | 저위험은 자동 통과, `REVIEW_REQUIRED`만 관리자에게 |

<br/>

## 화면 플로우

### SC-01 · 가입 / 로그인

<img src="assets/sc01-register.png" width="880" alt="회원가입 화면" />

공개 회원가입으로 생성되는 계정은 임직원 권한으로 시작하며, 관리자 권한은 별도 프로비저닝으로 부여됩니다.

<br/>

### SC-02 · Tool 찾기 — 업무 목적만 입력합니다

<img src="assets/sc02-discover-input.png" width="880" alt="업무 목적 입력 화면" />

**데이터 등급 선택 항목이 없습니다.** 업무 설명 문맥에서 시스템이 민감도를 판정하기 때문입니다.<br/>
필요한 기능 키워드와 고급 설정은 모두 선택 사항입니다.

<br/>

### SC-03 · 점검·추천 결과

판정 배지, 판정 사유, 신뢰도, 점검 번호가 함께 제시됩니다.

<img src="assets/sc03-result-approved.png" width="880" alt="사전 점검 결과 - 사용 가능" />

이어서 업무에 활용할 수 있는 Tool 후보가 **추천 점수 · 남은 라이선스**와 함께 정렬됩니다.<br/>
좌석이 남아 있으면 `즉시 신청`, 좌석이 0석이면 `구매 승인 요청`으로 버튼이 갈립니다.

<img src="assets/sc03-tool-cards.png" width="880" alt="추천 Tool 카드" />

모든 판정에는 **근거가 된 정책 문서의 실제 구간**이 관련도 점수와 함께 따라붙습니다.

<img src="assets/sc03-policy-evidence.png" width="880" alt="판정에 사용한 정책 문서 근거" />

<br/>

### SC-04 · 내 신청 / 점검 이력

신청한 Tool의 판정 결과, 라이선스 출처(`AVAILABLE_LICENSE` · `NEW_PURCHASE`), 신청 상태를 한곳에서 추적합니다.

<br/>

### SC-05 · 관리자 콘솔

보안 검토 대기, 구매 승인 대기, 좌석 부족 Tool, 등록 라이선스 비용을 한 화면에서 확인합니다.

<img src="assets/sc05-admin-dashboard.png" width="880" alt="관리자 운영 현황" />

Tool별 메타데이터와 라이선스 재고를 직접 관리하고, 사내 보안정책 문서를 업로드·활성화합니다.

<img src="assets/sc05-admin-tools.png" width="880" alt="Tool 관리" />

<br/>

## 두 가지 시나리오로 보는 판정

<table>
<tr>
<th width="50%">AT-01 · 저위험 업무는 자동 통과</th>
<th width="50%">AT-02 · 민감정보는 검토 큐로</th>
</tr>
<tr>
<td valign="top">

입력: *"매주 반복되는 회의 리포트를 만들고 싶어요"*

<img src="assets/sc02-discover-input.png" alt="저위험 업무 입력" />

</td>
<td valign="top">

입력: *"고객 주민등록번호 반복 입력이 힘들어요"*

<img src="assets/sc02-discover-pii.png" alt="민감정보 업무 입력" />

</td>
</tr>
<tr>
<td valign="top">

**결과 — 사용 가능** (신뢰도 94%)

<img src="assets/sc03-result-approved.png" alt="사용 가능 판정" />

보유 라이선스로 **즉시 신청**. 관리자 개입이 없습니다.

</td>
<td valign="top">

**결과 — 보안 검토 필요** (신뢰도 82%)

<img src="assets/sc03-result-review.png" alt="보안 검토 필요 판정" />

사용자가 `PII`라고 쓰지 않았는데도 시스템이 개인정보를 감지하고, **사용 조건**과 **추가 확인이 필요한 정보**를 제시한 뒤 검토 큐에 적재합니다.

</td>
</tr>
</table>

민감정보 업무에서는 모든 Tool 카드가 `조건부 검토` 상태로 잠기고, 보안 담당자의 확인 이후에만 신청이 열립니다.

<img src="assets/sc03-review-cards.png" width="880" alt="조건부 검토 상태의 Tool 카드" />

<br/>

## 시스템 아키텍처

Spring Cloud 기반 MSA입니다. Eureka 서비스 디스커버리, OAuth2 인증 서버, API Gateway 뒤에 4개의 Spring Boot 서비스와 1개의 FastAPI RAG 서비스가 있고, Vue 3 SPA가 앞단에 붙습니다.

```mermaid
flowchart TB
    subgraph L1["① Client"]
        VUE["vue-frontend — Vue 3 + Vite SPA<br/>PublicLayout · AppLayout · AdminLayout<br/>Pinia · axios(unwrap/raw)"]
    end

    subgraph L2["② Edge / Discovery"]
        direction LR
        GW["API Gateway :8080<br/>라우팅 · CORS · JWT 검증"]
        AU["Auth Server :9000<br/>OAuth2 · JWK Set"]
        EU["Eureka :8761<br/>Service Registry"]
        GW --> AU
    end

    subgraph L3["③ Microservices"]
        direction LR
        US["user-service :8081<br/>사용자·부서·직무"]
        CS["course-service :8082<br/>Tool 카탈로그·라이선스"]
        ES["enrollment-service :8083<br/>도입 신청·점검 이력"]
        PS["payment-service :8084<br/>라이선스 결제"]
    end

    subgraph L4["④ RAG Engine — recommend-service :8085 (FastAPI)"]
        direction LR
        RR["router · service"]
        DOC["documents<br/>청킹"] --> EMB["embedding<br/>vector+keyword"] --> RET["retriever<br/>top_k=6"] --> PE["policy_engine<br/>APPROVED · CONDITIONAL<br/>REVIEW_REQUIRED · DENIED"]
        PE -.-> LLM["llm (옵션)"]
        RR --> DOC
    end

    subgraph L5["⑤ Kafka"]
        direction LR
        T1[["payment.completed"]]
        T2[["enrollment.completed"]]
    end

    subgraph L6["⑥ MariaDB — lecture_db"]
        direction LR
        D1[("users · departments<br/>job_roles")]
        D2[("courses · enrollments<br/>payments")]
        D3[("precheck_requests<br/>precheck_tool_results")]
        D4[("policy_documents<br/>policy_chunks<br/>precheck_evidences")]
    end

    VUE ==>|"Vite proxy · REST"| GW
    GW ==> US & CS & ES & PS & RR
    US & CS & ES & PS & RR -.->|"register"| EU
    ES -->|"WebClient"| CS
    ES -->|"WebClient"| PS
    RR -->|"내부 API · X-Internal-Key"| ES
    RR -->|"내부 API · X-Internal-Key"| CS
    PS -.->|"produce"| T1
    T1 -.->|"consume"| ES
    ES -.->|"produce"| T2
    T2 -.->|"consume"| RR
    US --> D1
    CS --> D2
    PS --> D2
    ES --> D3
    RET --> D4

    classDef f fill:#e3f2fd,stroke:#1976d2,color:#0d47a1
    classDef e fill:#fff3e0,stroke:#ef6c00,color:#e65100
    classDef s fill:#e8f5e9,stroke:#2e7d32,color:#1b5e20
    classDef r fill:#f3e5f5,stroke:#7b1fa2,color:#4a148c
    classDef k fill:#fff8e1,stroke:#f9a825,color:#f57f17
    classDef d fill:#fce4ec,stroke:#c2185b,color:#880e4f
    class VUE f
    class GW,AU,EU e
    class US,CS,ES,PS s
    class RR,DOC,EMB,RET,PE,LLM r
    class T1,T2 k
    class D1,D2,D3,D4 d
```

### 사전점검 요청이 흐르는 경로

```mermaid
sequenceDiagram
    autonumber
    actor U as 임직원
    participant FE as Vue SPA
    participant GW as API Gateway
    participant RS as recommend-service
    participant RET as retriever
    participant DB as policy_chunks
    participant PE as policy_engine
    participant ES as enrollment-service

    U->>FE: 업무 목적 자연어 입력
    FE->>GW: POST /api/recommend/precheck (Bearer JWT)
    GW->>RS: JWT 검증 후 라우팅
    RS->>RET: 질의 임베딩 + 키워드 하이브리드 검색
    RET->>DB: 관련 정책 구간 top-k 조회
    DB-->>RET: RetrievedChunk[]
    RET-->>PE: 근거 전달
    PE->>PE: 데이터 민감도 추론 + 정책 조항 대조
    PE-->>RS: 판정 + 정책 근거 + Tool 추천 랭킹
    RS->>ES: 점검 이력·근거 저장 (X-Internal-Key)
    RS-->>FE: 결과 반환
    FE-->>U: 판정 배지 · 근거 · Tool 카드
```

<br/>

## 기술 스택

| 영역 | 사용 기술 |
| --- | --- |
| **Frontend** | Vue 3, Vite, Vue Router, Pinia, Tailwind CSS, axios |
| **Backend** | Spring Boot 3, Spring Cloud Gateway, Spring Data JPA, Spring Security (OAuth2 Resource Server), WebClient |
| **RAG Service** | Python, FastAPI, Pydantic, 하이브리드 검색 (벡터 + 키워드), OpenAI 호환 LLM 연동(옵션) |
| **Service Discovery** | Netflix Eureka |
| **Auth** | OAuth2 Authorization Server, JWT, JWK Set |
| **Messaging** | Apache Kafka (KRaft), DLT 기반 실패 처리 |
| **Database** | MariaDB 11.2 |
| **Infra** | Docker, Docker Compose, Gradle |

<br/>

## 서비스 구성

| 서비스 | 포트 | 설명 |
| --- | --- | --- |
| `vue-frontend` | 3000 | Vue 3 SPA |
| `api-gateway` | 8080 | 단일 진입점 |
| `auth-server` | 9000 | OAuth2 토큰 발급 |
| `eureka-server` | 8761 | 서비스 레지스트리 |
| `user-service` | 8081 | 사용자 · 조직 |
| `course-service` | 8082 | Tool 카탈로그 · 라이선스 |
| `enrollment-service` | 8083 | 도입 신청 · 점검 이력 |
| `payment-service` | 8084 | 라이선스 결제 |
| `recommend-service` | 8085 | RAG 보안 사전점검 · 추천 |
| `mariadb` | 3379 → 3306 | `lecture_db` |
| `kafka` | 9092 | 이벤트 브로커 |

기동 순서는 `depends_on` 헬스체크로 강제됩니다.

```
MariaDB / Kafka  →  Eureka  →  Auth Server  →  API Gateway + 4개 서비스  →  Recommend Service
```

<br/>

## 실행 방법

```bash
git clone https://github.com/5jo-s/In-house-SaaS-Security-Pre-inspection-Platform.git
cd In-house-SaaS-Security-Pre-inspection-Platform

# 공통 이미지 로드 (API Gateway, Auth Server)
docker load -i infra-images.tar

# 백엔드 전체 기동
docker compose build --no-cache && docker compose up -d

# 서비스 등록 상태 확인 → http://localhost:8761
# 프론트엔드 실행
cd vue-frontend && npm install && npm run dev   # http://localhost:3000
```

> [!NOTE]
> 브라우저 호출은 반드시 Vite 프록시를 통해야 합니다. 게이트웨이 CORS 허용 목록이 `http://localhost:3000`으로 고정되어 있어, `127.0.0.1:3000`이나 LAN IP로 접속하면 preflight가 403으로 실패합니다.

<br/>

## 저장소 · 문서

| | |
| --- | --- |
| **메인 저장소** | [In-house-SaaS-Security-Pre-inspection-Platform](https://github.com/5jo-s/In-house-SaaS-Security-Pre-inspection-Platform) |
| **PRD** | [docs/PRD_final.md](https://github.com/5jo-s/In-house-SaaS-Security-Pre-inspection-Platform/blob/main/docs/PRD_final.md) — 문제 정의, 가설 H-0~H-3, 화면 플로우, MVP 범위 |
| **명세 · 보고서** | [docs/](https://github.com/5jo-s/In-house-SaaS-Security-Pre-inspection-Platform/tree/main/docs) — API 명세, 요구사항 명세, ERD, 테스트 보고서 |
| **DB 스키마** | [init-db/](https://github.com/5jo-s/In-house-SaaS-Security-Pre-inspection-Platform/tree/main/init-db) |
| **시드 · 검증 스크립트** | [scripts/seed/](https://github.com/5jo-s/In-house-SaaS-Security-Pre-inspection-Platform/tree/main/scripts/seed) |

<br/>

---

<div align="center">
<sub>SKALA Agile · MSA 실습 프로젝트 — 7반 5조</sub>
</div>
