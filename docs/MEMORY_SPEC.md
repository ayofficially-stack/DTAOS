# DTAOS Memory Layer Specification

Version: 1.0

---

# Purpose

Memory Layer는 DTAOS의 경험과 상태를 관리하는 계층이다.

Knowledge가 "무엇을 알고 있는가"를 저장한다면,

Memory는 "무엇을 했는가"와 "현재 무엇을 하고 있는가"를 관리한다.

Memory는 Project의 실행 과정에서 생성되는 경험을 축적하고,

다음 의사결정에 활용하는 것을 목적으로 한다.

---

# Responsibility

Memory Layer는 다음을 관리한다.

1. Runtime State
2. Daily Memory
3. Weekly Review
4. Monthly Review
5. Decisions
6. Lessons
7. History

---

# Root Structure

```text
memory/
├── runtime/
├── daily/
├── weekly/
├── monthly/
├── decisions/
├── lessons/
└── history/
```

---

# Memory Responsibilities

| Folder | Responsibility |
|----------|----------------|
| runtime | 현재 실행 상태 |
| daily | 일일 작업 기록 |
| weekly | 주간 회고 |
| monthly | 월간 회고 |
| decisions | 반복 의사결정 기록 |
| lessons | 경험에서 얻은 교훈 |
| history | 장기 보관 기록 |

---

# Memory Lifecycle

```text
Runtime

↓

Daily

↓

Weekly

↓

Monthly

↓

Lessons

↓

Knowledge
```

---

# Lifecycle Definition

## Runtime

현재 진행 중인 상태

---

## Daily

하루 동안 수행한 작업

---

## Weekly

주간 단위 회고

---

## Monthly

월간 단위 개선

---

## Lessons

재사용 가능한 경험

---

## Knowledge

검증 완료 후 Knowledge Layer로 승격

---

# Storage Rules

1. Runtime에는 현재 상태만 저장한다.
2. Daily는 하루 단위 기록만 저장한다.
3. Weekly는 Daily를 요약한다.
4. Monthly는 Weekly를 요약한다.
5. Lessons는 반복 가치가 있는 경험만 저장한다.
6. Knowledge 승격 전까지 Lessons에 유지한다.
7. History는 수정하지 않는다.

---

# Relationship

```text
Project

↓

Runtime

↓

Daily

↓

Weekly

↓

Monthly

↓

Lessons

↓

Knowledge
```

---

# Decision Relationship

Decision은 Memory의 일부이다.

```text
Project

↓

Decision

↓

Result

↓

Lesson

↓

Knowledge
```

---

# Promotion Rules

Lesson은 다음 조건을 만족하면 Knowledge로 승격한다.

- 반복 사용 가능
- 실제 프로젝트 검증 완료
- 근거 존재
- 다른 프로젝트 적용 가능

---

# Anti-patterns

Memory에 저장하지 않는다.

- 공통 기술 자료
- 회사 소개
- 제품 설명
- 논문 요약
- 특허 설명

이들은 Knowledge Layer에 저장한다.

---

# Standard Metadata

모든 Memory는 가능하면 아래 정보를 포함한다.

```text
Date

Project

Owner

Status

Related Decision

Related Lesson

Last Updated
```

---

# Dependency Principle

Memory는 실행하지 않는다.

Memory는 기록하고 복원한다.

```text
Project

↓

Memory

↓

Knowledge
```

Memory는 Engine을 직접 호출하지 않는다.

---

# Design Philosophy

Memory는 기록을 위한 저장소가 아니다.

Memory는

경험을 자산으로 만드는 시스템이다.

좋은 Memory는

같은 실수를 반복하지 않게 한다.

---

# Success Metric

좋은 Memory Layer란

많은 기록을 저장하는 것이 아니라,

필요한 경험을

필요한 순간에

빠르게 복원하여

더 나은 의사결정을 만드는 시스템이다.

---

# Status

Specification Version : 1.0

Layer Status : Frozen

Architecture : Approved