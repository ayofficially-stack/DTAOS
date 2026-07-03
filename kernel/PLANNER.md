# DTAOS Planner

Version: 1.0

---

# Purpose

Planner는 사용자 요청을 바로 실행하지 않고, 먼저 실행 계획을 수립한다.

DTAOS는 즉시 답변하지 않는다.

먼저 무엇을 해야 하는지 판단하고,

필요한 순서를 설계한 뒤,

Dispatcher로 전달한다.

---

# Core Principle

Plan First.

Execute Second.

Answer Last.

---

# Responsibility

Planner는 다음을 결정한다.

1. 요청의 목적
2. 최종 산출물
3. 필요한 작업 단계
4. 필요한 입력 정보
5. 예상 리스크
6. 실행 순서
7. 중단 또는 질문 필요 여부

---

# Execution Pipeline

```text
User Request

↓

Planner

↓

Execution Plan

↓

Dispatcher

↓

Engine Orchestrator

↓

Engine Execution

↓

Analysis Synthesizer

↓

Adaptive Persona Engine

↓

Decision Engine

↓

Quality Gate

↓

Final Output
```

---

# Planning Steps

## STEP 1

Request Understanding

확인 항목

- 사용자가 원하는 결과는 무엇인가?
- 문서 작성인가?
- 검토인가?
- 의사결정인가?
- 시스템 리팩터링인가?

---

## STEP 2

Output Definition

확인 항목

- 최종 출력 형식
- 필요한 상세 수준
- 사용자가 바로 적용 가능한 형태인지
- 파일 생성이 필요한지 여부

---

## STEP 3

Context Requirement

확인 항목

- 현재 Project가 필요한가?
- Knowledge가 필요한가?
- 이전 Decision이 필요한가?
- 외부 정보 또는 최신 정보가 필요한가?

---

## STEP 4

Execution Path

확인 항목

- 어떤 Dispatcher Route가 필요한가?
- 어떤 Engine이 필요한가?
- 어떤 Workflow가 필요한가?
- Persona Review가 필요한가?
- Decision Engine이 필요한가?

---

## STEP 5

Risk Check

확인 항목

- 근거 부족
- 정보 부족
- 과장 위험
- 기술적 불확실성
- 사업적 리스크
- 사용자의 의도와 산출물 불일치

---

## STEP 6

Clarification Decision

Planner는 다음 조건에서 질문해야 한다.

- 목표가 불명확하다.
- 입력 자료가 부족하다.
- 선택지가 여러 개이고 결과가 크게 달라진다.
- 최신 정보 확인이 필요하다.
- 사용자의 승인이 필요한 구조 변경이다.

질문이 필요하지 않으면 즉시 Dispatcher로 전달한다.

---

# Output Format

Planner는 내부적으로 아래 형식을 만든다.

```text
Planning Summary:

User Goal:

Output Type:

Required Context:

Execution Route:

Required Engines:

Required Workflow:

Required Reviewers:

Risk Flags:

Clarification Needed:

Next Step:
```

---

# Default Planning Routes

## Government Proposal

```text
Planner

↓

Dispatcher

↓

Government Engine

↓

Technical Engine

↓

Business Engine

↓

Adaptive Persona Engine

↓

Decision Engine

↓

Quality Gate
```

---

## Sales Material

```text
Planner

↓

Dispatcher

↓

Business Engine

↓

Design Engine

↓

Presentation Engine

↓

Analysis Synthesizer

↓

Adaptive Persona Engine

↓

Decision Engine

↓

Quality Gate
```

---

## Technical Review

```text
Planner

↓

Dispatcher

↓

Technical Engine

↓

Analysis Synthesizer

↓

Adaptive Persona Engine

↓

Decision Engine

↓

Quality Gate
```

---

## System Refactoring

```text
Planner

↓

Dispatcher

↓

Architecture Review

↓

Migration Plan

↓

Implementation

↓

Quality Gate
```

---

# Anti-patterns

Planner가 해서는 안 되는 일:

- 요청을 분석하지 않고 바로 답변
- 필요한 Context를 확인하지 않고 실행
- 무조건 모든 Engine 실행
- 모든 Reviewer 호출
- 질문이 필요한 상황에서 임의로 가정
- 실행 계획 없이 산출물 생성

---

# Relationship with Dispatcher

Planner는 실행 계획을 세운다.

Dispatcher는 그 계획을 실제 Route로 변환한다.

```text
Planner = What should be done?

Dispatcher = Where should it go?
```

---

# Success Criteria

좋은 Planner는

사용자가 요청한 일을

바로 답하기 전에

가장 짧고 정확한 실행 경로로 변환한다.

---

# Status

Version : 1.0

Architecture : Approved