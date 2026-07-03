# DTAOS Engine Orchestrator

Version: 1.0

---

# Purpose

Engine Orchestrator는 Dispatcher가 선택한 여러 Engine을 실행 순서에 따라 호출하고, 각 Engine의 결과를 하나의 분석 결과로 통합한다.

Dispatcher는 어떤 Engine을 사용할지 결정한다.

Engine Orchestrator는 선택된 Engine을 어떻게 실행할지 결정한다.

---

# Responsibility

Engine Orchestrator는 다음을 관리한다.

1. Engine 실행 순서
2. Engine별 입력 전달
3. Engine 결과 수집
4. Engine 간 충돌 확인
5. 통합 분석 결과 생성
6. Adaptive Persona Engine으로 전달

---

# Execution Pipeline

```text
Dispatcher

↓

Engine Orchestrator

↓

Selected Engines

↓

Engine Findings

↓

Integrated Engine Analysis

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

# Engine Execution Rule

Engine은 병렬적으로 선택될 수 있지만,

결과 통합은 반드시 순차적으로 수행한다.

기본 순서:

```text
1. Primary Engine

2. Secondary Engine

3. Supporting Engine

4. Integrated Analysis
```

---

# Default Engine Order

## Sales Material

```text
Business Engine

↓

Design Engine

↓

Presentation Engine
```

이유:

Sales Material은 먼저 “팔리는가”를 확인한 뒤,

시각적 완성도와 전달력을 검토한다.

---

## Presentation Material

```text
Presentation Engine

↓

Design Engine

↓

Business Engine
```

이유:

Presentation은 먼저 “이해되는가”를 확인한 뒤,

시각 구조와 사업적 설득력을 검토한다.

---

## Technical Material

```text
Technical Engine

↓

Business Engine

↓

Presentation Engine
```

이유:

기술자료는 먼저 “기술적으로 맞는가”를 확인한 뒤,

적용 가치와 전달력을 검토한다.

---

## Government Proposal

```text
Government Engine

↓

Technical Engine

↓

Business Engine

↓

Presentation Engine
```

이유:

정부과제는 평가기준을 먼저 확인하고,

기술성, 사업성, 전달력을 순서대로 검토한다.

---

# Engine Output Contract

각 Engine은 반드시 아래 형식으로 결과를 반환한다.

```text
Engine:

Input Summary:

Key Findings:

Strengths:

Weaknesses:

Risks:

Recommendations:

Score:

Failure Conditions Detected:
```

---

# Integrated Analysis Format

Engine Orchestrator는 각 Engine 결과를 아래 형식으로 통합한다.

```text
Selected Engines:

Execution Order:

Engine Findings Summary:

Cross-Engine Conflicts:

Common Risks:

Priority Recommendations:

Input to Adaptive Persona Engine:
```

---

# Cross-Engine Conflict Types

| Conflict | Meaning |
|---|---|
| Business vs Design | 사업 메시지를 강화하면 디자인 밀도가 높아지는 충돌 |
| Design vs Presentation | 시각적으로는 좋지만 읽는 흐름이 약한 충돌 |
| Technical vs Business | 기술은 강하지만 고객 가치가 약한 충돌 |
| Government vs Marketing | 표현은 좋지만 평가 기준에는 약한 충돌 |
| Evidence vs CTA | 근거를 강화하면 행동 유도가 약해지는 충돌 |

---

# Conflict Handling Rule

1. 충돌을 숨기지 않는다.
2. 어떤 Engine의 판단을 우선할지 명시한다.
3. 우선순위는 Task Type에 따라 결정한다.
4. 충돌은 수정 방향으로 변환한다.

---

# Priority Rule

## Sales Material

Business 우선.

그 다음 Design.

그 다음 Presentation.

---

## Presentation Material

Presentation 우선.

그 다음 Design.

그 다음 Business.

---

## Technical Material

Technical 우선.

그 다음 Business.

그 다음 Presentation.

---

## Government Proposal

Government 우선.

그 다음 Technical.

그 다음 Business.

그 다음 Presentation.

---

# Anti-patterns

Engine Orchestrator가 해서는 안 되는 일:

- Engine 결과 없이 Reviewer에게 바로 전달
- 모든 Engine을 무조건 실행
- Task와 무관한 Engine 실행
- Score만 평균 내서 결론 도출
- Engine 간 충돌을 무시
- Quality Gate 생략

---

# Output Rule

Engine Orchestrator의 출력은 최종 답변이 아니다.

Engine Orchestrator의 출력은 Adaptive Persona Engine과 Decision Engine의 입력이다.

---

# Status

Specification Version : 1.0

Layer Status : Active

Architecture : Approved