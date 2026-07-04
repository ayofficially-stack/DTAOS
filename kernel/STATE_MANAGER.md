# DTAOS State Manager

Version: 1.0

Status: Beta

---

# Purpose

State Manager는 Project의 현재 실행 상태(State)를 관리한다.

DTAOS는 항상 현재 상태를 먼저 확인한 후 작업을 수행한다.

동일한 Project는 언제든지 이전 상태부터 이어서 실행할 수 있어야 한다.

---

# Core Principles

State Before Planning

Planning Before Execution

Execution Before Memory

Memory Before Knowledge

---

# Execution Pipeline

User Request

↓

Project Registry

↓

Project State

↓

Planner

↓

Dispatcher

↓

Execution

↓

State Update

↓

Execution Log

↓

Memory

---

# Responsibilities

State Manager는 다음 정보를 관리한다.

- Current Phase
- Current Section
- Current Task
- Waiting Items
- Blockers
- Next Task
- Last Execution
- Completion Status

---

# State Lifecycle

NOT_STARTED

↓

PLANNING

↓

READY

↓

RUNNING

↓

REVIEW

↓

WAITING

↓

RUNNING

↓

COMPLETED

↓

ARCHIVED

---

# State Definitions

## NOT_STARTED

프로젝트가 생성되었지만 아직 시작하지 않음.

---

## PLANNING

실행 계획 수립 중.

---

## READY

실행 준비 완료.

---

## RUNNING

현재 작업 수행 중.

---

## REVIEW

검토 단계.

---

## WAITING

외부 입력 또는 사용자 응답 대기.

예)

- 시험성적서
- 시장자료
- 고객 피드백
- 실험 결과

---

## COMPLETED

프로젝트 종료.

---

## ARCHIVED

보관 상태.

---

# Project State Format

Current Phase:

Current Section:

Current Task:

Waiting Items:

Blockers:

Next Task:

Completion:

Last Updated:

---

# Example

Project

P001

Current Phase

RUNNING

Current Section

2. 성장가능성

Current Task

2-2 시장수요 작성

Waiting Items

- 시장규모 통계

Blockers

없음

Next Task

2-3 사업화 전략

Completion

38%

Last Updated

2026-07-03

---

# State Transition Rules

RUNNING

↓

REVIEW

↓

RUNNING

↓

WAITING

↓

RUNNING

↓

COMPLETED

State는 항상 현재 상태만 가진다.

이전 상태는 Execution Log에서 관리한다.

---

# Recovery Rule

DTAOS 시작 시

Project Registry

↓

PROJECT_STATUS.md

↓

Current State 복원

↓

Planner 실행

↓

Dispatcher 실행

사용자가

"P001 계속"

이라고 입력하면

State Manager는 현재 상태부터 복원한다.

---

# Update Rules

다음 경우 State를 갱신한다.

- Task 완료
- Section 완료
- Review 완료
- Waiting 진입
- Waiting 해제
- Project 완료

---

# Relationship

Project Registry

↓

State Manager

↓

Planner

↓

Dispatcher

↓

Execution

↓

Execution Log

↓

Memory

---

# Anti-patterns

State Manager는

- 프로젝트 내용을 저장하지 않는다.
- Knowledge를 저장하지 않는다.
- Engine 결과를 저장하지 않는다.
- Decision을 저장하지 않는다.

State만 관리한다.

---

# Success Criteria

좋은 State Manager는

사용자가

"P001 계속"

이라고 입력하면

현재 작업 위치를 복원하고

다음 작업을 즉시 이어서 수행할 수 있다.

---

# Status

Version : 1.0

Architecture : Approved