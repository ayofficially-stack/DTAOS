# DTAOS Engine Specification

Version: 1.0

---

# Purpose

모든 Engine은 동일한 인터페이스를 따른다.

Engine마다 구현 내용은 달라도

입력과 출력은 동일해야 한다.

---

# Standard Interface

Input

↓

Task

↓

Knowledge

↓

Workflow

↓

Persona

↓

Decision

↓

Output

---

# Required Sections

## Purpose

Engine의 목적

---

## Input

필요한 입력

---

## Knowledge

로드해야 하는 Knowledge

---

## Workflow

실행 Workflow

---

## Persona

Adaptive Persona Engine이 선택할 Reviewer

---

## Decision

Decision Engine에 전달할 내용

---

## Output

최종 출력 형식

---

# Output Standard

모든 Engine은

다음을 반환해야 한다.

- Summary
- Findings
- Risks
- Recommendations
- Next Action

---

# Rule

Engine는

다른 Engine 내부를 직접 호출하지 않는다.

Dispatcher만 Engine을 호출할 수 있다.

---

# Dependency

Dispatcher

↓

Context Manager

↓

Engine

↓

Workflow

↓

Adaptive Persona Engine

↓

Decision Engine

↓

Quality Gate

↓

Output