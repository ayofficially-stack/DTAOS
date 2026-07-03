# Adaptive Persona Engine

Version: 1.0

---

## Purpose

Adaptive Persona Engine은 자료의 성격에 따라 Reviewer Pool 10명 중 관련 있는 3~5명만 선택하여 검증하는 시스템이다.

---

## Components

ReviewerPool

↓

Selector

↓

WeightManager

↓

ConflictResolver

---

## Execution Flow

1. Dispatcher가 Task Type을 전달한다.
2. Selector가 관련 Reviewer 3~5명을 선택한다.
3. WeightManager가 Reviewer 가중치를 적용한다.
4. 각 Reviewer가 독립적으로 검토한다.
5. ConflictResolver가 충돌 의견을 정리한다.
6. 최종 통합 의견을 생성한다.
7. Quality Gate로 전달한다.

---

## Core Principle

10명을 모두 호출하지 않는다.

관련 있는 3~5명만 호출한다.

---

## Output

Adaptive Persona Engine의 최종 출력은 다음 형식을 따른다.

```text
Selected Reviewers

Common Findings

Conflicts

Top 3 Revisions

Unified Recommendation
```