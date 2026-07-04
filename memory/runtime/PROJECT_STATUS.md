# DTAOS Project Status

Version: 2.0

Status: Active

---

# Purpose

PROJECT_STATUS는 현재 Project의 실행 상태(State)를 관리한다.

이 파일은 프로젝트의 진행률을 기록하는 것이 아니라,

현재 어디까지 진행되었고,
무엇을 하고 있으며,
다음에 무엇을 해야 하는지를 관리한다.

DTAOS는 프로젝트 실행 시 반드시 이 파일을 먼저 읽는다.

---

# Project Information

Project ID:

Project Name:

Project Type:

Owner:

Created Date:

Last Updated:

---

# Current State

State:

- NOT_STARTED
- PLANNING
- READY
- RUNNING
- REVIEW
- WAITING
- COMPLETED
- ARCHIVED

Current State:

---

# Current Execution

Current Phase:

Current Workflow:

Current Section:

Current Task:

Current Step:

---

# Progress

Overall Progress:

Phase Progress:

Current Milestone:

---

# Waiting Items

-

-

-

---

# Blockers

-

-

-

---

# Next Actions

Next Task:

Expected Output:

Required Inputs:

Required Knowledge:

Required Engines:

Required Reviewers:

---

# Last Execution

Execution ID:

Execution Date:

Execution Result:

Execution Summary:

---

# Decision Summary

Latest Decision:

Decision Confidence:

Pending Decisions:

---

# Quality Status

Last Quality Gate:

Quality Result:

Remaining Issues:

---

# Runtime Memory

Temporary Notes:

-

-

-

---

# Knowledge Candidates

Candidate 1:

Candidate 2:

Candidate 3:

---

# Lessons Learned

Lesson 1:

Lesson 2:

Lesson 3:

---

# Update Rules

PROJECT_STATUS는 다음 상황에서 반드시 갱신한다.

- Phase 변경
- Section 완료
- Task 완료
- Waiting 진입
- Waiting 해제
- Review 완료
- Decision 변경
- Project 완료

---

# State Transition

```text
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
RUNNING
      ↓
WAITING
      ↓
RUNNING
      ↓
COMPLETED
      ↓
ARCHIVED
```

---

# Recovery Rules

DTAOS 실행 시 다음 순서로 복원한다.

```text
PROJECT_STATUS.md

↓

Current State

↓

Current Phase

↓

Current Workflow

↓

Current Section

↓

Current Task

↓

Planner

↓

Dispatcher

↓

Execution
```

이미 완료된 Task는 다시 수행하지 않는다.

WAITING 상태에서는 Waiting Item을 우선 확인한다.

---

# Relationship

```text
Project Registry

↓

PROJECT_STATUS

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

↓

Knowledge Promotion
```

---

# Anti-patterns

PROJECT_STATUS는

- 프로젝트 산출물을 저장하지 않는다.
- Knowledge를 저장하지 않는다.
- Engine 분석 결과를 저장하지 않는다.
- Reviewer 의견을 저장하지 않는다.

현재 실행 상태(State)만 관리한다.

---

# Success Criteria

좋은 PROJECT_STATUS는

사용자가

```text
DTAOS 시작

P001 계속
```

이라고 입력하면,

현재 작업 위치를 즉시 복원하고

다음 작업을 이어서 수행할 수 있어야 한다.

---

# Status

Version: 2.0

Architecture: Beta

Approved: Yes