# DTAOS Dispatcher

Version: 2.0

---

# Purpose

Dispatcher는 DTAOS의 중앙 라우팅 엔진(Central Routing Engine)이다.

Planner가 생성한 실행 계획을 바탕으로

- 어떤 Project를 사용할지
- 어떤 Context를 로드할지
- 어떤 Engine을 실행할지
- 어떤 Workflow를 적용할지
- 어떤 Persona를 호출할지

를 결정한다.

Dispatcher는 실행 경로(Route)를 결정하지만,
직접 분석하거나 답변하지 않는다.

---

# Execution Pipeline

```text
User Request

↓

Planner

↓

Project Registry Lookup

↓

Intent Analysis

↓

Project Detection

↓

Context Loading

↓

Engine Selection

↓

Workflow Selection

↓

Engine Orchestrator

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

# Project Registry Lookup

Dispatcher는 Project Detection 전에 반드시 Project Registry를 확인한다.

사용자 요청에 Project ID(P001, P002...)가 포함된 경우,

`config/PROJECT_REGISTRY.md`를 조회하여 프로젝트 정보를 복원한다.

---

## Lookup Flow

```text
User Input

↓

Project ID Detection

↓

PROJECT_REGISTRY.md

↓

Project Folder

↓

PROJECT_CONTEXT.md

↓

PROJECT_STATUS.md

↓

Dispatcher Routing
```

---

## Rule

- Project ID가 존재하면 Registry를 먼저 조회한다.
- Registry에 없는 Project는 자동 생성하지 않는다.
- Project를 찾지 못하면 사용자에게 확인을 요청한다.

---

# Intent Categories

## Government

Examples

- NET
- 정부과제
- 사업계획서
- 기술수요조사서
- RFP

Primary Engine

Government Engine

Supporting Engines

Technical Engine

Business Engine

Presentation Engine

---

## Sales

Examples

- White-label
- Sales Sheet
- Company Profile
- Brochure

Primary Engine

Business Engine

Supporting Engines

Design Engine

Presentation Engine

---

## Technical

Examples

- Graphene
- Composite
- Carbide
- Coating
- Textile

Primary Engine

Technical Engine

Supporting Engines

Business Engine

---

## Presentation

Examples

- PPT
- Pitch Deck
- 발표자료

Primary Engine

Presentation Engine

Supporting Engines

Design Engine

Business Engine

---

## Decision

Examples

- 투자
- 우선순위
- 전략

Primary Engine

Decision Engine

Supporting Engines

Business Engine

Technical Engine

---

# Context Loading Rule

Dispatcher는 Repository 전체를 읽지 않는다.

필요한 Context만 선택적으로 로드한다.

---

## Government

```text
skills/

↓

knowledge/certifications

↓

knowledge/company

↓

knowledge/technology

↓

Project Context
```

---

## Sales

```text
knowledge/company

↓

knowledge/products

↓

knowledge/market

↓

knowledge/customers

↓

knowledge/lessons

↓

Project Context
```

---

## Technical

```text
knowledge/technology

↓

knowledge/products

↓

knowledge/cases

↓

Project Context
```

---

# Engine Selection Rule

Dispatcher는 모든 Engine을 실행하지 않는다.

Task에 필요한 Engine만 선택한다.

각 Task는

- Primary Engine
- Supporting Engine

으로 구성한다.

선택된 Engine은 Engine Orchestrator에게 전달된다.

---

# Workflow Selection

Dispatcher는 Task Type에 따라 Workflow를 선택한다.

Examples

Government

↓

WF001_Government

Sales

↓

WF002_Sales

Presentation

↓

WF003_Presentation

Technical

↓

WF004_Technical

---

# Persona Selection

Dispatcher는 Persona를 직접 선택하지 않는다.

Adaptive Persona Engine에게 아래 정보를 전달한다.

- Task Type
- Industry
- Target Audience
- Project Context
- Selected Engines

Adaptive Persona Engine은

10명의 Reviewer 중

3~5명을 선택한다.

---

# Routing Table

Government

↓

Government Engine

↓

Technical Engine

↓

Business Engine

↓

Presentation Engine

↓

Engine Orchestrator

↓

Analysis Synthesizer

↓

Adaptive Persona Engine

↓

Decision Engine

↓

Quality Gate

---

Sales

↓

Business Engine

↓

Design Engine

↓

Presentation Engine

↓

Engine Orchestrator

↓

Analysis Synthesizer

↓

Adaptive Persona Engine

↓

Decision Engine

↓

Quality Gate

---

Technical

↓

Technical Engine

↓

Business Engine

↓

Engine Orchestrator

↓

Analysis Synthesizer

↓

Adaptive Persona Engine

↓

Decision Engine

↓

Quality Gate

---

# Output Policy

Dispatcher는 최종 답변을 생성하지 않는다.

Dispatcher는 다음 정보를 다음 Layer로 전달한다.

- Project
- Context
- Selected Engines
- Workflow
- Routing Information

최종 답변 생성은 Quality Gate 이후에만 수행한다.

---

# Core Principles

- Plan Before Route
- Project First
- Context Before Execution
- Execute Only Required Engines
- Route Before Answer
- Never Skip Quality Gate

---

# Status

Version : 2.0

Architecture : Beta

Status : Approved