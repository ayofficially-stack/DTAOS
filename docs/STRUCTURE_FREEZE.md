# DTAOS Structure Freeze

Version: 1.0

---

# Purpose

이 문서는 DTAOS v1.0의 최상위 아키텍처를 정의한다.

DTAOS의 모든 기능은 이 구조를 기반으로 개발한다.

이 문서 이후에는 최상위 폴더를 임의로 추가하거나 삭제하지 않는다.

구조 변경이 필요한 경우 반드시 Change Control 절차를 따른다.

---

# Architecture Principles

DTAOS는 네 개의 계층(Layer)으로 구성된다.

## 1. System Layer

시스템을 실행하는 계층이다.

```
kernel
engines
workflows
automation
config
```

---

## 2. Knowledge Layer

AI가 사용하는 지식과 자산을 관리한다.

```
knowledge
skills
prompts
templates
personas
```

---

## 3. Execution Layer

실제 업무(Project)를 수행하는 계층이다.

```
projects
modules
```

---

## 4. Memory Layer

현재 상태와 장기 기억을 관리한다.

```
memory
dashboards
```

---

# Frozen Root Structure

```text
DTAOS/
├── automation/
├── config/
├── dashboards/
├── docs/
├── engines/
├── kernel/
├── knowledge/
├── memory/
├── modules/
├── personas/
├── projects/
├── prompts/
├── skills/
├── templates/
├── workflows/
└── README.md
```

---

# Root Folder Responsibilities

| Folder | Responsibility |
|----------|----------------|
| automation | 반복 작업, 자동화, 알림, 스케줄링 |
| config | 시스템 설정, Registry, Version 관리 |
| dashboards | 운영 현황 및 상태 시각화 |
| docs | 아키텍처, Boot, Loader, 운영 문서 |
| engines | 기능별 실행 엔진 |
| kernel | Dispatcher, Context, Quality Gate, State Recovery |
| knowledge | 공통 지식 저장소 |
| memory | Runtime, Lessons, Decisions, History |
| modules | 업무 기능 모듈 |
| personas | Reviewer 정의 |
| projects | 실제 업무(Project)의 최상위 실행 단위 |
| prompts | 재사용 가능한 Prompt |
| skills | 특정 업무 수행 방법론 |
| templates | 문서 및 결과물 Template |
| workflows | 업무 실행 절차 |
| README.md | Repository Entry Point |

---

# Design Rules

1. 새로운 Root Folder는 생성하지 않는다.

2. 새로운 기능은 기존 Layer 안에서 해결하는 것을 원칙으로 한다.

3. Layer 추가는 최후의 선택이다.

4. Project는 DTAOS의 최상위 실행 단위(Aggregate Root)이다.

5. 모든 작업은 반드시 하나의 Project에 속해야 한다.

6. 공통 지식은 `knowledge/`에 저장한다.

7. 실행 로직은 `kernel/`, `engines/`, `workflows/`에 저장한다.

8. 현재 상태는 `memory/runtime/`에서 관리한다.

9. 장기 의사결정은 Project의 `DECISIONS.md` 또는 `memory/decisions/`에 저장한다.

10. 새로운 기능을 추가하기 전에 기존 구조를 재사용할 수 있는지 먼저 검토한다.

---

# Dependency Principle

DTAOS는 아래 방향으로만 의존한다.

```
Project

↓

Dispatcher

↓

Context

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
```

상위 Layer는 하위 Layer를 사용할 수 있지만,

하위 Layer는 상위 Layer를 직접 참조하지 않는다.

---

# Change Control

구조 변경이 필요한 경우 반드시 아래 내용을 기록한다.

| Item | Description |
|------|-------------|
| Date | 변경 일자 |
| Version | 적용 버전 |
| Change | 변경 내용 |
| Reason | 변경 사유 |
| Impact | 영향 범위 |
| Approved By | 승인자 |

---

# Design Philosophy

DTAOS는

- Document Repository가 아니다.
- Prompt Collection이 아니다.
- AI Chat History도 아니다.

DTAOS는 **Project-Centric AI Operating System**이다.

모든 기능은 Project를 중심으로 동작한다.

Project는 Knowledge를 사용하고,

Workflow를 실행하며,

Persona의 검증을 받고,

Decision을 생성하고,

Memory를 축적한다.

---

# Success Metric

좋은 DTAOS란

폴더가 많은 시스템이 아니다.

새로운 프로젝트를 빠르게 시작하고,

복잡한 업무를 일관된 방식으로 수행하며,

좋은 의사결정을 반복적으로 만들어내는 시스템이다.

---

# Status

Architecture Version : **1.0**

Structure Status : **Frozen**

Development Phase : **Sprint 3**