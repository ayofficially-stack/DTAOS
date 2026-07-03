# DTAOS Engine Execution Specification

Version: 1.0

---

# Purpose

Engine은 DTAOS의 실행 단위이다.

Engine은 단순히 선택되는 것이 아니라, 지정된 기준에 따라 분석을 수행하고 결과를 생성해야 한다.

Reviewer는 Engine 결과를 검증한다.

Decision Engine은 Engine 결과와 Reviewer 의견을 통합한다.

---

# Core Principle

Engine First.

Reviewer Second.

Decision Last.

---

# Standard Engine Interface

모든 Engine은 아래 구조를 따른다.

```text
Purpose

Inputs

Execution Steps

Outputs

Metrics

Failure Conditions

Quality Gate Link
```

---

# Execution Pipeline

```text
Dispatcher

↓

Context Manager

↓

Engine Execution

↓

Workflow

↓

Adaptive Persona Engine

↓

Conflict Resolver

↓

Decision Engine

↓

Quality Gate

↓

Final Output
```

---

# Required Sections

## 1. Purpose

Engine이 수행하는 핵심 역할을 정의한다.

---

## 2. Inputs

Engine이 분석에 필요한 입력을 정의한다.

예시:

- Document
- Slide
- Project Context
- Knowledge
- User Goal
- Target Audience

---

## 3. Execution Steps

Engine이 반드시 수행해야 하는 분석 절차를 정의한다.

Execution Steps는 가능한 한 체크리스트 형태로 작성한다.

---

## 4. Outputs

Engine이 생성해야 하는 결과물이다.

기본 출력:

```text
Summary

Findings

Strengths

Weaknesses

Risks

Recommendations
```

---

## 5. Metrics

Engine이 평가할 기준이다.

Metrics는 재현 가능해야 한다.

좋은 Metric은 다음 조건을 만족한다.

- 반복 평가 가능
- 비교 가능
- 설명 가능
- Quality Gate와 연결 가능

---

## 6. Failure Conditions

Engine이 실패로 판단해야 하는 조건이다.

Failure Condition이 발생하면 최종 출력 전에 수정이 필요하다.

---

## 7. Quality Gate Link

Engine 결과는 반드시 `kernel/QUALITY_GATE.md`로 전달된다.

Quality Gate는 Engine 결과를 최종 검증한다.

---

# Engine Output Standard

모든 Engine은 아래 형식을 기본 출력으로 사용한다.

```text
Engine:

Purpose:

Input Summary:

Execution Findings:

Strengths:

Weaknesses:

Risks:

Recommendations:

Failure Conditions Detected:

Next Action:
```

---

# Reviewer Relationship

Reviewer는 Engine을 대체하지 않는다.

Reviewer는 Engine 결과를 검토한다.

```text
Engine Analysis

↓

Reviewer Review

↓

Conflict Resolution

↓

Decision
```

---

# Decision Relationship

Decision Engine은 다음 입력을 받아야 한다.

```text
Engine Findings

Reviewer Findings

Conflicts

Risks

Recommendations
```

Decision Engine은 이를 바탕으로 실행 우선순위를 제시한다.

---

# Anti-patterns

Engine이 해서는 안 되는 일:

- Reviewer처럼 주관적 의견만 제시
- 분석 없이 바로 결론 제시
- Quality Gate 생략
- Metrics 없이 점수만 제시
- 근거 없이 Confidence 부여
- 프로젝트 Context 없이 일반론 출력

---

# Status

Specification Version : 1.0

Layer Status : Active

Architecture : Approved