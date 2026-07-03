# DTAOS Project Layer Specification

Version: 1.0

---

# Purpose

Project는 DTAOS의 최상위 실행 단위(Aggregate Root)이다.

모든 작업은 반드시 하나의 Project에 속한다.

Project는

- Knowledge를 사용하고
- Engine을 실행하며
- Workflow를 수행하고
- Persona의 검증을 받고
- Decision을 생성하며
- Memory를 축적한다.

Project는 DTAOS의 모든 기능을 연결하는 중심 객체이다.

---

# Responsibility

Project Layer는 다음을 관리한다.

1. Project Context
2. Project Goal
3. Project Scope
4. Project Execution
5. Project Outputs
6. Project Decisions
7. Project Reviews
8. Project Retrospective

---

# Standard Structure

```text
projects/
├── README.md
├── PROJECT_SPEC.md
│
├── P000_Template/
│
├── P001_xxx/
│
├── P002_xxx/
│
└── ...
```

---

# Standard Project Structure

모든 Project는 아래 구조를 따른다.

```text
Pxxx_ProjectName/

README.md

PROJECT_CONTEXT.md

PROJECT_STATUS.md

DECISIONS.md

OUTPUTS.md

REVIEW.md

PROJECT_LOG.md

RETROSPECTIVE.md
```

---

# Project Lifecycle

```text
Create

↓

Plan

↓

Research

↓

Execute

↓

Review

↓

Improve

↓

Complete

↓

Archive
```

---

# Required Metadata

모든 Project는 아래 메타데이터를 가진다.

```text
Project ID

Project Name

Owner

Priority

Status

Current Phase

Created

Last Updated

Completion
```

---

# Dependency Principle

Project는 아래 Layer를 사용한다.

```text
Project

↓

Knowledge

↓

Kernel

↓

Context

↓

Engine

↓

Workflow

↓

Persona

↓

Decision

↓

Memory

↓

Output
```

Project는 Layer를 직접 구현하지 않는다.

필요한 Layer를 호출하여 실행한다.

---

# Relationship

```text
Project

↓

Knowledge

↓

Execution

↓

Decision

↓

Output

↓

Lessons

↓

Knowledge
```

Project는 Knowledge를 소비하고,

새로운 Knowledge를 생성한다.

---

# Project States

| State | Meaning |
|--------|---------|
| Planning | 계획 |
| Research | 조사 |
| Execution | 수행 |
| Review | 검토 |
| Improvement | 개선 |
| Completed | 완료 |
| Archived | 보관 |

---

# Storage Rules

Project 내부에는

- 프로젝트 전용 문서
- 프로젝트 산출물
- 프로젝트 의사결정
- 프로젝트 로그

만 저장한다.

공통 정보는 Knowledge Layer에 저장한다.

---

# Promotion Rules

프로젝트에서 생성된 내용은 아래 기준으로 승격한다.

Output

↓

Lesson

↓

Knowledge Review

↓

Knowledge Base

---

# Anti-patterns

Project 안에 저장하지 않는다.

- 회사 공통 소개
- 기술 플랫폼 설명
- 시장 공통 정보
- 반복 사용하는 Prompt
- 공통 Template

---

# Standard Template

Project 문서는 아래 구조를 따른다.

```text
Purpose

Scope

Inputs

Outputs

Dependencies

Status

Next Action
```

---

# Success Criteria

모든 Project는 아래 질문에 답할 수 있어야 한다.

- 우리는 무엇을 만드는가?
- 왜 만드는가?
- 현재 어디까지 진행되었는가?
- 다음 작업은 무엇인가?
- 언제 완료되는가?

---

# Design Philosophy

Project는 문서 묶음이 아니다.

Project는 실행 단위이다.

DTAOS는 Project를 중심으로 동작한다.

Knowledge는 Project를 지원하고,

Memory는 Project를 기억하며,

Engine은 Project를 실행한다.

---

# Success Metric

좋은 Project Layer란

프로젝트를 많이 저장하는 것이 아니라,

프로젝트를 끝까지 완수하고,

그 경험을 다음 프로젝트에 재사용할 수 있도록 만드는 시스템이다.

---

# Status

Specification Version : 1.0

Layer Status : Frozen

Architecture : Approved