# DTAOS Knowledge Layer Specification

Version: 1.0

---

# Purpose

Knowledge Layer는 DTAOS가 반복적으로 사용하는 공통 지식과 검증된 정보를 관리하는 계층이다.

Knowledge는 특정 프로젝트에 종속되지 않는다.

여러 Project, Engine, Workflow가 공유할 수 있는 자산만 Knowledge에 저장한다.

Knowledge Layer의 목적은 반복 가능한 업무를 빠르고 일관되게 수행하도록 지원하는 것이다.

---

# Responsibility

Knowledge Layer는 다음 영역을 관리한다.

1. Company Knowledge
2. Technology Knowledge
3. Product Knowledge
4. Market Knowledge
5. Certification / Government Knowledge
6. Customer Knowledge
7. Lessons Learned
8. Historical Cases

---

# Root Structure

```text
knowledge/
├── company/
├── technology/
├── products/
├── market/
├── certifications/
├── customers/
├── lessons/
└── cases/
```

---

# Knowledge Responsibilities

| Category | Description |
|-----------|-------------|
| company | 회사 소개, 비전, 포지셔닝 |
| technology | 핵심 기술, 메커니즘, 플랫폼 |
| products | 제품 및 서비스 |
| market | 시장 정보 및 산업 동향 |
| certifications | 인증, 특허, 정부사업 |
| customers | 고객, 파트너, PoC |
| lessons | 반복 업무에서 얻은 교훈 |
| cases | 완료된 프로젝트 사례 |

---

# Storage Rules

1. 여러 프로젝트에서 재사용 가능한 정보만 저장한다.
2. 프로젝트 전용 정보는 `projects/<ProjectID>/`에 저장한다.
3. 검증되지 않은 정보는 공식 Knowledge로 저장하지 않는다.
4. 임시 메모는 `memory/runtime/` 또는 Project Log에 저장한다.
5. 의사결정은 Project의 `DECISIONS.md` 또는 `memory/decisions/`에 저장한다.
6. 반복적으로 활용 가능한 교훈은 `knowledge/lessons/`로 승격한다.

---

# Knowledge Lifecycle

```text
Draft

↓

Verified

↓

Reusable

↓

Deprecated

↓

Archived
```

---

## Lifecycle Definitions

### Draft

검증되지 않은 초안

---

### Verified

근거가 확인된 지식

---

### Reusable

여러 프로젝트에서 사용할 수 있는 지식

---

### Deprecated

더 이상 권장되지 않는 지식

---

### Archived

보존만 하는 지식

---

# Evidence Levels

Knowledge는 반드시 근거 수준을 가진다.

| Level | Evidence |
|--------|----------|
| A | 실측 데이터, 시험성적서, 공식 문서 |
| B | 논문, 특허, 기술보고서 |
| C | 전문가 의견, 회의록, 실무 경험 |
| D | 가설, 아이디어, 추정 |

---

# Knowledge Quality Rules

Knowledge는 다음 조건 중 하나 이상을 만족해야 한다.

- 실제 데이터 또는 공식 문서에 근거한다.
- 반복 업무에서 검증되었다.
- 출처가 명확하다.
- "가설" 또는 "검증 필요"가 명시되어 있다.
- 프로젝트 회고에서 재사용 가치가 확인되었다.

---

# Ownership

모든 Knowledge는 다음 메타데이터를 포함하는 것을 권장한다.

```text
Owner

Reviewer

Status

Evidence Level

Last Updated
```

---

# Relationship with Projects

Knowledge는 Project를 지원한다.

Project는 Knowledge를 소비(Use)하고,

새로운 경험을 만들어낸다.

```text
Knowledge

↓

Project Execution

↓

Lessons Learned

↓

Verification

↓

Knowledge Base
```

Knowledge는 Project를 대체하지 않는다.

Project는 Knowledge를 생성하고,

Knowledge는 다음 Project를 지원한다.

---

# Knowledge Promotion Workflow

새로운 Knowledge는 아래 절차를 따라 승격한다.

```text
Project

↓

Lessons Learned

↓

Verification

↓

Knowledge Review

↓

Knowledge Base
```

승격 기준

- 최소 1회 이상 실제 업무에서 검증
- 다른 프로젝트에서도 재사용 가능
- 출처와 맥락이 명확
- 기존 Knowledge와 충돌하지 않음

---

# Anti-patterns

Knowledge에 저장하지 않는다.

- 임시 아이디어
- 프로젝트 전용 산출물
- 검증되지 않은 주장
- 일회성 대화
- 오래되어 신뢰할 수 없는 정보
- 개인적인 메모
- 감정적인 의견

---

# Standard Template

Knowledge 문서는 가능하면 아래 구조를 따른다.

```text
Purpose

Source / Basis

Key Facts

Evidence

Use Cases

Limitations

Related Files

Owner

Reviewer

Status

Last Updated
```

---

# Dependency Principle

Knowledge는 Engine을 참조하지 않는다.

Knowledge는 실행하지 않는다.

Knowledge는 저장만 한다.

```text
Knowledge

↓

Context

↓

Engine

↓

Workflow

↓

Output
```

---

# Design Philosophy

Knowledge는 정보 저장소가 아니다.

Knowledge는

재사용 가능한 업무 자산(Reusable Business Asset)이다.

좋은 Knowledge는

여러 Project에서 반복적으로 활용될 수 있어야 한다.

---

# Success Metric

좋은 Knowledge Layer란

정보가 많은 저장소가 아니라,

필요한 정보를

필요한 순간에

빠르게 불러와

반복 가능한 성과를 만드는 시스템이다.

---

# Status

Specification Version : **1.0**

Layer Status : **Frozen**

Architecture : **Approved**